# Python Versioning Experiments

This repo is used to understand the limitations of specifying the
version of a Python package and version ordering as defined in the
[Version Specifiers in the Python Packaging User Guide](https://packaging.python.org/en/latest/specifications/version-specifiers/).

The table below shows the order in which the package versions were
created. It is different from how the packages will be ordered in the
[Test Python Package Index](https://test.pypi.org/project/pythonversioningexperiments/).

| Written version   | Normalized version| Commit                                   | Notes                   |
| :---------------: | :---------------: | :--------------------------------------: | :---------------------- |
| 0.1.0             | 0.1.0             | [cd74719](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/cd747197cfd8d7c0c3e33e15be8f76af145c68c6) |                         |
| 0.2               | 0.2               | [6b79a04](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/6b79a044d47a225a51207d830e1739d19f908514) |                         |
| 00.03.000.00000.0 | 0.3.0.0.0         | [ca32933](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/ca329332c241113d413d2fbde603c1a488465359) | Extra zeros in numeric sub-segments are removed during version normalization. |
| v0.4.0            | 0.4.0             | [0f55d7e](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/0f55d7e9590cfb7d14b2780d68995a9952963ca3) | The letter "v" is removed during version normalization. |
| 1_alpha0           | 1a0              | [b1af02a](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/b1af02ad70a3a52e2f045c9bc5d45c183695995f) |  |
| 1-a1               | 1a1              | [e1af9ea](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/e1af9ea033c803301210503a25d67e84299e1242) |  |
| 1.b                | 1b0              | [c6be52e](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/c6be52ed752c3dd9f9baca561cd2d353f8135f1e) |  |
| 1beta1             | 1b1              | [283a93d](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/283a93dd92f7039d32aee89b340e3978cc8ac7a3) |  |
| 1-preview          | 1rc0             | [03bf6cd](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/03bf6cd417c653da8ba2413f8caae2467a131067) |  |
| 1-pre1             | 1rc1             | [f8a12f6](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/f8a12f6e825a4e52c0f407d9f6e2460142a8fe90) |  |
| 1-pre1             | 1rc1             | [f8a12f6](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/f8a12f6e825a4e52c0f407d9f6e2460142a8fe90) |  |
| 1b2                | 1b2              | [fa59417](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/fa594177289f3a75856778f1d480e7fbe2b012ad) | Posting a beta release after a release candidate does not make the beta release to be considered greater than the release candidate already created. |
| 1b3                | 1b3              | [15696a7](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/15696a799573fda618073a51215738c4cb4351ed) | Posting a beta release after a release candidate does not make the beta release to be considered greater than the release candidate already created. |
| 1.0_c2             | 1.0rc2           | [84ad55d](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/84ad55dc8d1eba222173cbfa9077eb0472113b86) | Adding a new subsegment with value 0 to the final release segment does not functionally affect the package. From the TestPyPI perspective this release is equivalent to 1rc2 or 1.0.0.0.0.rc2. For installation we can use any of the mentioned versions, because the final pip redirects us to the current version. |
| 1.0_b.5             | 1.0b5           | [7b842e1](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/7b842e1e4b97c92965e1c95353c1e0b60745234b) | Posting a beta release after a candidate release does not make the beta release considered better than the candidate release already created, even if a 0 subsegment has been added at the end of the release segment. |
| 1rc3                | 1rc3             | [fabe2fb](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/fabe2fbba00d9655e3df220b30b05b7b153147d8) |  |
| 1.0.0               | 1.0.0            | [3fa4ef1](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/3fa4ef17ed93b93d57d2e7f814c794bf7d4646c6) |  |
| 1.0.0.post0         | 1.0.0.post0      | [2fc8160](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/2fc8160b9c4e58b9da8895688918e433ae51b6a8) |  |
| 1.0.0rev_1          | 1.0.0.post1      | [0b892cb](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/0b892cb20446783e534dd48f992cf3c3a9575306) |  |
| 1.0.0-R-2           | 1.0.0.post2      | [30657f3](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/30657f3f0b563c40ae5448d7faf447373db32c54) |  |
| 1.0.0-3             | 1.0.0.post3      | [8e99bdb](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/8e99bdb1ecdce8afcd0574210b63656896c864b9) | A post-release can also be created by omitting the “post”, if “-” is used together with a numeric value. |
| 1.0.0-3             | 1.0.0.post3      | [b71b8f1](https://github.com/GabrielGiurgica/python-versioning-experiments/commit/b71b8f102dcf85207e7faa64fb35540817b1b70e) | “Creating post-releases of pre-releases is strongly discouraged.” ([Source](https://packaging.python.org/en/latest/specifications/version-specifiers/#post-releases)) |