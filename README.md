# python-docs-dist

> We no longer provide pre-built PDFs of the documentation. To build a PDF archive, follow the instructions in the [Developer's Guide](https://devguide.python.org/documentation/start-documenting/#building-the-documentation) and run `make dist-pdf` in the `Doc/` directory of a copy of the CPython repository.\
[Python documentation downloads page](https://docs.python.org/download.html)

Since building PDFs isn't as simple as building other formats, this project's aim is to spare you from inconvenience of doing it yourself as well as provide other formats of downloadable documentation and easy way to build it yourself using GitHub Actions.

## Usage

If you just want the files, download desired version from [Releases](https://github.com/ViktorVoloshko/python-docs-dist/releases).

If you want to build them yourself:
1. [Fork this repository](https://github.com/ViktorVoloshko/python-docs-dist/fork)
2. (Optional) Review and change options in [.env](./.env)
3. Go to _Actions_ and run _Build_ workflow

Then, after successful build, grab artifacts from _Actions_. If you want them in _Releases_, create and push a tag that honors [versioning model](#versioning).

If your build fails, check [Troubleshooting](#troubleshooting) section.

## Versioning

Tags and releases follow `python_version.build` versioning model where `build` is a build number. Builds are numbered sequentially, starting with 1.

## Troubleshooting

Here are some known building caveats:
- *(PDF)* Starting with version 3.14, building requires rsvg-convert tool to be available in system's PATH
- In versions up to 3.12, `Makefile` lacks a step to ensure that `dist` directory exists before trying to store build artifacts there, which leads to an error if it wasn't created manually
- Building version 3.10 requires [`imghdr` module](https://docs.python.org/3/library/imghdr.html), which was removed in >=3.13

## License

While the source code in this repository is original, all distributed artifacts are derived from the [official CPython repository](https://github.com/python/cpython).

| Component | License |
| --- | --- |
| Source code | [GNU GPLv3](./LICENSE) |
| Distributed artifacts | [Python's license](https://docs.python.org/license.html) |
