# Python Versioning Experiments

This repo is used to understand the limitations of specifying the version of a Python package as defined in the [Version Specifiers in the Python Packaging User Guide](https://packaging.python.org/en/latest/specifications/version-specifiers/).

| Written version   | Normalized version| Commit                                   | Notes                   |
| :---------------: | :---------------: | :--------------------------------------: | :---------------------- |
| 0.1.0             | 0.1.0             | cd747197cfd8d7c0c3e33e15be8f76af145c68c6 |                         |
| 0.2               | 0.2               | 6b79a044d47a225a51207d830e1739d19f908514 |                         |
| 00.03.000.00000.0 | 0.3.0.0.0         | ca329332c241113d413d2fbde603c1a488465359 | Extra zeros in numeric sub-segments are removed during version normalization. |
| v0.4.0            | 0.4.0             | 0f55d7e9590cfb7d14b2780d68995a9952963ca3 | The letter "v" is removed during version normalization. |