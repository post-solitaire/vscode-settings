# vscode-settings \([README на русском](README.ru-RU.md)\)

This is a repo for settings of my Visual Studio Code setup. I'm trying to keep the settings explicit and deliberate so that I don't have to set things up each time I wipe my system or work remotely (not on my main laptop). I'm also tired of remembering what each setting is doing and why I set it up this way a year later.

This is a utility repo mostly for myself, not really a public-facing project. But I hope it helps others, so I made it public.



# External file as `settings.json`

`settings.json` can be a symlink, [apparently](https://github.com/microsoft/vscode/issues/194856), and VS Code will follow it transparently. Just copy the settings file to a separate location (for example in your projects folder) while VS Code is closed and create a symlink back to it:
```bash
cd ~/.config/Code/User
mv settings.json ~/projects/vscode-settings/
ln -s $HOME/projects/vscode-settings settings.json
```
Now any settings you change via UI or in the settings file, will be reflected in the new "external" file. You can also change them in the "external" file and VS Code will follow. And since the file is now outside of the VS Code's own config folder, you can add it to a git repo (like I did here), or whatever you want to do with it.

> [!NOTE]
> I'm using one `settings.json` file for all my profiles, so this works. If you're using per-profile settings, this may not be suitable for you.

The same could be done with `keybindings.json`.
