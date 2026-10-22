# tetriz-py: the LLM service for the Tetriz Harness recommendations engine.
# Exposes POST /api/v1/generate-content (the three harness LLM tasks) and
# POST /api/v1/classify-themes. The Gemini key is supplied at run time via
# TETRIZ_GEMINI_API_KEY (or GEMINI_API_KEY) and is never baked into the image.
# python:3.11-slim
FROM python:3.11-slim@sha256:e88e9763f943ec1834f992a4b51e0f24500486803e8bc534e5767af9ea65f6ce

WORKDIR /app

# Pin uv for reproducible dependency resolution.
ARG UV_VERSION=0.13.5
RUN pip install --no-cache-dir "uv==${UV_VERSION}"

# Resolve the locked dependency set first for layer caching. --no-install-project installs
# only third-party deps; --no-dev and no --extra means the optional ML stack (torch /
# sentence-transformers, the `ml` extra) is intentionally excluded — the SBERT theme
# strategy ships disabled, and the Gemini strategy needs none of it.
COPY pyproject.toml uv.lock ./
RUN uv sync --frozen --no-dev --no-install-project

COPY app ./app
RUN uv sync --frozen --no-dev --no-editable

# The project licence, its notice and the third-party inventory travel with the image. LICENSE here is a
# copy of the repository's root LICENSE, because the build context is this directory.
COPY LICENSE NOTICE THIRD_PARTY_LICENSES.md /usr/share/licenses/tetriz-py/
COPY third_party/licenses/ /usr/share/licenses/tetriz-py/native/

ENV PYTHONUNBUFFERED=1
# Make the project's virtualenv the default interpreter path.
ENV PATH="/app/.venv/bin:$PATH"
# "prod" hides /docs; a host targeting development overrides TETRIZ_ENVIRONMENT at run time.
ENV TETRIZ_ENVIRONMENT=prod
# Inside the container the server must listen on all interfaces, or Docker's published port
# cannot reach it. The localhost-only guard for this unauthenticated service is applied at the
# PORT PUBLISH instead (docker-compose binds the host port to 127.0.0.1). The bare-metal run
# keeps its loopback default from the config (TETRIZ_HOST defaults to 127.0.0.1).
ENV TETRIZ_HOST=0.0.0.0
ENV TETRIZ_PORT=8000

# Run as a non-root user.
RUN useradd --system --create-home --uid 10001 appuser && chown -R appuser:appuser /app
USER appuser

EXPOSE 8000
CMD ["python", "-m", "app.main"]
