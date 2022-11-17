[![!CyVerse Learning Center](assets/logos/krai_logo.png "CyVerse Learning Center"){ width="400" }](https://krai.ai){target=_blank}

# AXS Overview
Re-design based on the previous CK framework's kernel with a user friendly CLI.

## Installation

Simply download the repository.

```{bash eval=False}
git clone https://github.com/krai/axs ~/axs
Add the path to bashrc.

echo "export PATH='$PATH:$HOME/axs'" >> ~/.bashrc
And source it.

source ~/.bashrc
Upon sucessful installation.

user@laptop:~/axs$ axs
DefaultKernel{}
```

## How-to guides

The dependencies of various components are managed through axs entries. To start with, entries can be found in ~/axs/core_collection. When programs are being executed for the first time, new entries will be automatically stored in work collection. By default, they are located at ~/work_collection.

