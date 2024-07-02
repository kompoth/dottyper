# dottyper

Dotfiles manager based on [Typer](https://github.com/tiangolo/typer).

## Install

To use Dottyper you'll need to build it using Poetry and install it in your
user environment. Here is how (replace `X.Y` with the actual package version):
```bash
poetry build
pipx install dist/dottyper-X.Y-py3-none-any.whl
```

When the package is installed, run `dottyper --install-completion` to get
command completion for your shell.

## Usage

Run `dottyper --help` to get usage hints.

You'll need to write a configuaration file, `./dottyper.yaml` by default, to
manage your files. It basically has this structure:
```yaml
# Create soft links to these files
symlinks:
  - destination: $HOME                          # Where to create soft links
    location: $HOME/Documents/repos/dotfiles/   # Where the files are located
    files:                                      # File names
    - .bashrc
    - .vimrc
  - destination: $HOME/.config                  # Here comes another batch
    location: $HOME/Documents/repos/dotfiles/config
    files:
    - alacritty
    - lsd
# Download these files
downloads:
  - destination: $HOME/.urxvt/ext               # Where to put downloads
    urls:                                       # List of URLs
    - https://raw.githubusercontent.com/majutsushi/urxvt-font-size/master/font-size 
  - destination: $HOME/Media                    # Here comes another batch
    urls:
    - https://picsum.photos/id/237/200/300
```
