# savedots 

It is a simple dotfiles manager script.

It requires `jq` and `git` installed.

## Usage
### Save your dotfiles
- Download the script and run `./savedots install` to copy it to `/usr/local/bin`
- Create the `~/.config/savedots.json` file
```json
{
    "remoterepo": "https://github.com/...git",
    "files": [
        {
            "name": "name-of-file-in-the-repo",
            "path": "~/.config/path/to/file"
        },
        ...
    ]
}
```
The file `name` can be something like `hypr/hyprland.conf` to create a subdirectory in the repo

- Run `savedots init` to create the repo (in `~/.cache/savedots`)
- Make some changes to files or add other files to the config file
- Run `savedots` to commit and push changes (if you delete che `~/.cache/savedots` directory running `savedots` will clone the repo you specified in the config file)

### Recover dotfiles from a repo
- Clone and cd into the repo (there should be `savedots` and `savedots.json`)
- Run `./savedots install`
- Run `savedots cp`
- Make some changes to files or add other files to the config file
- Run `savedots` to commit and push changes
