# Clean Installations on Mac

I've found for teaching and writing tutorials that I regularly need to go through and do clean-installations of tools on my computer so I can make updated explanations on setting up tools on machines. 

These are mostly commands to remove preferences and other cached files. **This goes beyond dragging an Application to the trash, but also removes login, extensions, and other preferences**

Here is a non-definitive list of things I use:

## Clean VSCode Install

In CLI:

```sh
rm -fr ~/Library/Preferences/com.microsoft.VSCode.helper.plist \
rm -fr ~/Library/Preferences/com.microsoft.VSCode.plist \
rm -fr ~/Library/Caches/com.microsoft.VSCode \
rm -fr ~/Library/Caches/com.microsoft.VSCode.ShipIt/ \
rm -fr ~/Library/Application\ Support/Code/ \
rm -fr ~/Library/Saved\ Application\ State/com.microsoft.VSCode.savedState/ \
rm -fr ~/.vscode/ \
rm -rf ~/.vscode*
```

Thanks [j7nn7k on StackOverflow](https://stackoverflow.com/a/47561948)

## Clean GitHub Desktop

```sh
rm -fr ~/Library/Application\ Support/GitHub\ Desktop/ \
rm -fr ~/Library/Caches/com.github.GitHubClient \
rm -fr ~/Library/Caches/com.github.GitHubClient.ShipIt \
rm -fr ~/Library/Preferences/com.github.Electron.plist \
rm -fr ~/Library/Preferences/com.github.GitHubClient.plist
```