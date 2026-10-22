# Third-party licences

These are the third-party Python packages tetriz-py installs at run time, at the versions `uv.lock` pins, with
each package's SPDX licence expression. The dev dependency group is not installed in the image and is not
listed. The licence is the package's declared `License-Expression`, or, where
a package declares none, the SPDX identifier for its `License` field or licence classifier. Each installed
package also carries its full licence text in its `.dist-info` directory.

`tests/test_license_files.py` fails when a locked runtime package or version is missing from these tables.

## Runtime

Installed by `uv sync --no-dev`, and so present in the image.

| Package | Version | Licence | Installed when |
|---|---|---|---|
| annotated-doc | 0.0.5 | MIT | always |
| annotated-types | 0.8.0 | MIT | always |
| anyio | 4.15.1 | MIT | always |
| certifi | 2026.10.19 | MPL-2.0 | always |
| cffi | 2.1.1 | MIT-0 | CPython |
| charset-normalizer | 3.5.2 | MIT | always |
| click | 8.5.0 | BSD-3-Clause | always |
| cryptography | 50.0.2 | Apache-2.0 OR BSD-3-Clause | always |
| distro | 1.9.0 | Apache-2.0 | always |
| fastapi | 0.143.0 | MIT | always |
| google-auth | 2.61.0 | Apache-2.0 | always |
| google-genai | 2.29.0 | Apache-2.0 | always |
| h11 | 0.16.0 | MIT | always |
| httpcore | 1.0.9 | BSD-3-Clause | always |
| httptools | 0.9.0 | MIT | always |
| httpx | 0.28.1 | BSD-3-Clause | always |
| idna | 3.20 | BSD-3-Clause | always |
| opentelemetry-api | 1.45.1 | Apache-2.0 | always |
| prometheus-client | 0.26.0 | Apache-2.0 AND BSD-2-Clause | always |
| pyasn1 | 0.6.4 | BSD-2-Clause | always |
| pyasn1-modules | 0.4.2 | BSD-2-Clause | always |
| pycparser | 3.11 | BSD-3-Clause | CPython |
| pydantic | 2.14.0 | MIT | always |
| pydantic-core | 2.50.0 | MIT | always |
| pydantic-settings | 2.15.0 | MIT | always |
| python-dotenv | 1.2.4 | BSD-3-Clause | always |
| pyyaml | 6.0.3 | MIT | always |
| requests | 2.34.2 | Apache-2.0 | always |
| sniffio | 1.3.1 | MIT OR Apache-2.0 | always |
| starlette | 1.7.0 | BSD-3-Clause | always |
| structlog | 24.4.0 | MIT OR Apache-2.0 | always |
| tenacity | 9.1.4 | Apache-2.0 | always |
| typing-extensions | 4.16.0 | PSF-2.0 | always |
| typing-inspection | 0.4.4 | MIT | always |
| urllib3 | 2.8.0 | MIT | always |
| uvicorn | 0.54.0 | BSD-3-Clause | always |
| uvloop | 0.23.0 | MIT OR Apache-2.0 | CPython, not on Windows or Cygwin |
| watchfiles | 1.3.0 | MIT | always |
| websockets | 16.1.1 | BSD-3-Clause | always |

The image also holds uv 0.13.5 (MIT OR Apache-2.0), which the Dockerfile installs with pip to build the
virtualenv.

## Optional `ml` extra

Installed only by `uv sync --extra ml`, for the SBERT review-theme classifier. The image does not install it.
These are the packages the extra adds on top of the runtime set.

| Package | Version | Licence | Installed when |
|---|---|---|---|
| cloudpickle | 3.1.2 | BSD-3-Clause | always |
| colorama | 0.4.6 | BSD-3-Clause | Windows |
| filelock | 4.1.0 | MIT | always |
| fsspec | 2026.9.0 | BSD-3-Clause | always |
| hf-xet | 1.7.0 | Apache-2.0 | x86-64 or ARM64 |
| httpcore2 | 2.13.1 | BSD-3-Clause | not on Emscripten |
| httpx2 | 2.13.1 | BSD-3-Clause | always |
| httpx2-jsfetch | 1.0 | BSD-3-Clause | Emscripten, Python 3.12 or newer |
| huggingface-hub | 2.2.0 | Apache-2.0 | always |
| jinja2 | 3.1.6 | BSD-3-Clause | always |
| joblib | 1.6.0 | BSD-3-Clause | always |
| markdown-it-py | 4.2.0 | MIT | always |
| markupsafe | 3.0.4 | BSD-3-Clause | always |
| mdurl | 0.1.2 | MIT | always |
| mpmath | 1.3.0 | BSD-3-Clause | always |
| narwhals | 2.26.0 | MIT | always |
| networkx | 3.6.1 | BSD-3-Clause | Python 3.11 |
| networkx | 3.7 | BSD-3-Clause | Python 3.12 or newer |
| numpy | 2.4.6 | BSD-3-Clause AND 0BSD AND MIT AND Zlib AND CC0-1.0 | Python 3.11 |
| numpy | 2.5.3 | BSD-3-Clause AND 0BSD AND MIT AND Zlib AND CC0-1.0 | Python 3.12 or newer |
| packaging | 26.3 | Apache-2.0 OR BSD-2-Clause | always |
| pygments | 2.21.0 | BSD-2-Clause | always |
| regex | 2026.9.29 | Apache-2.0 AND CNRI-Python | always |
| rich | 15.0.0 | MIT | always |
| safetensors | 0.8.0 | Apache-2.0 | always |
| scikit-learn | 1.9.1 | BSD-3-Clause | always |
| scipy | 1.17.1 | BSD-3-Clause | Python 3.11 |
| scipy | 1.18.1 | BSD-3-Clause | Python 3.12 or newer |
| sentence-transformers | 5.7.0 | Apache-2.0 | always |
| setuptools | 84.0.0 | MIT | always |
| shellingham | 1.5.4 | ISC | always |
| sympy | 1.14.0 | BSD-3-Clause | always |
| threadpoolctl | 3.7.0 | BSD-3-Clause | always |
| tokenizers | 0.23.3 | Apache-2.0 | always |
| torch | 2.14.1 | Apache-2.0 AND Apache-2.0 WITH LLVM-exception AND BSD-2-Clause AND BSD-3-Clause AND BSL-1.0 AND MIT | not on Linux |
| torch | 2.14.1+cpu | Apache-2.0 AND Apache-2.0 WITH LLVM-exception AND BSD-2-Clause AND BSD-3-Clause AND BSL-1.0 AND MIT | Linux, from the PyTorch CPU index |
| tqdm | 4.70.1 | MPL-2.0 AND MIT | always |
| transformers | 5.19.0 | Apache-2.0 | always |
| truststore | 0.10.4 | MIT | not on Emscripten |
| typer | 0.27.3 | MIT | always |

The SBERT model the extra loads is not a Python package; its identity and licence are in the README's
[SBERT model](README.md#the-sbert-model) section.

## Licences that are not permissive

Every licence above is permissive except two weak-copyleft ones, both file-scoped:

- **certifi** (runtime) is MPL-2.0. The image installs it unmodified, as Python source, with its licence text
  in its `.dist-info` directory.
- **tqdm** (`ml` extra only) is MPL-2.0 AND MIT. The image does not install it.

## Container and bundled native components

The runtime wheels retain their upstream licence files. In addition, the Linux wheels of
cryptography 50.0.2 and uvloop 0.23.0 bundle OpenSSL 4.0.3 (Apache-2.0) and libuv 1.52.1
(MIT), respectively. Their licence texts are copied from the exact upstream tags into
`third_party/licenses/` and shipped under `/usr/share/licenses/tetriz-py/native/`:

- [OpenSSL 4.0.3](https://github.com/openssl/openssl/blob/openssl-4.0.3/LICENSE.txt)
- [libuv 1.52.1](https://github.com/libuv/libuv/blob/v1.52.1/LICENSE)

The base image also redistributes Debian packages, CPython and Python packaging tools.
Their licences remain in `/usr/share/doc/*/copyright`, `/usr/share/common-licenses/`,
`/usr/local/lib/python3.11/LICENSE.txt`, and the global site-packages metadata. These
include copyleft OS components: the permissive/weak-copyleft summary above describes
Python dependencies, not the whole container. Debian copyright files include applicable
source locations; distribution of images must also satisfy any source-provision obligations.

`scripts/image-licenses.py` in the repository root checks built images, their installed
package versions, retained licence payloads and these bundled native versions. It does
not establish the complete source provenance of every statically compiled Rust/C component
or certify compliance with all OS source-offer obligations. Repeat it for each distributed
architecture; wheel payloads can differ.
