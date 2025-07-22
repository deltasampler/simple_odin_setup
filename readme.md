# Simple Odin Setup
This is a simple guide for setting up Odin and Odin Language Server

## Table of Contents
- [Odin Setup](#odin-setup)
  - [Windows](#windows)
  - [Ubuntu](#ubuntu)
- [OLS Setup](#ols-setup)
  - [Windows](#windows-1)
  - [Ubuntu](#ubuntu-1)
- [OLS in VS Code](#ols-in-vs-code)
## Odin Setup
For more information check [official installation guide](https://odin-lang.org/docs/install/)
### Windows
* Download and install [Visual Studio](https://visualstudio.microsoft.com/) (Desktop development with C++)
* Clone Odin repository and run build script

      git clone https://github.com/odin-lang/Odin.git odin
      cd odin
      .\build.bat release
      del build.bat
* Add Odin directory to path in **Environment Variables**
### Ubuntu
* Install clang

      sudo apt install clang
* Clone Odin repository and run build script

      git clone https://github.com/odin-lang/Odin.git odin
      cd odin
      ./build_odin.sh release
* Add Odin directory to path in `.bashrc`

      echo 'export PATH="$PATH:<PATH_TO_ODIN>"' >> ~/.bashrc

      # if you have Odin in home directory
      echo 'export PATH="$PATH:$HOME/odin"' >> ~/.bashrc
## OLS Setup
OLS is Odin Language Server, for more information check [OLS repository](https://github.com/DanielGavin/ols)
### Windows
* Clone OLS repository and run build script

      git clone https://github.com/DanielGavin/ols.git
      cd ols
      .\build.bat
* Add OLS directory to path in **Environment Variables**
### Ubuntu
* Clone OLS repository and run build script

      git clone https://github.com/DanielGavin/ols.git
      cd ols
      ./build.sh
* Add OLS directory to path in `.bashrc`

      echo 'export PATH="$PATH:<PATH_TO_OLS>"' >> ~/.bashrc

      # if you have OLS in home directory
      echo 'export PATH="$PATH:$HOME/ols"' >> ~/.bashrc
## OLS in VS Code
* Install [OLS extension](https://marketplace.visualstudio.com/items?itemName=DanielGavin.ols)
* If you have OLS added to path, then set `ols.server.path` to `ols`
* If you don't have OLS added to path, then set `ols.server.path` to actual path of OLS executable
* Set `ODIN_ROOT` environment variable to path of Odin directory
* Optionally you can create `ols.json` file in project folder to configure OLS

      {
          "$schema": "https://raw.githubusercontent.com/DanielGavin/ols/master/misc/ols.schema.json",
          "collections": [
              {
                  "name": "<COLLECTION_NAME>",
                  "path": "<COLLECTION_PATH>"
              }
          ],
          "enable_semantic_tokens": false,
          "enable_document_symbols": true,
          "enable_hover": true,
          "enable_snippets": true,
          "profile": "default",
          "profiles": [
              {
                  "name": "default",
                  "checker_path": ["source"]
              },
          ]
      }
