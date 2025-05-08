# Nx 21 New TUI Task Hanging Repro

```shell
# Install dependencies
npm ci
# Serve the Angular application
npx nx serve new-tui-tasks-hanging
# After exiting the TUI, either by pressing Ctrl+C or 'q', the child process will not exit.
# Run the same command again to observe the hanging process:
npx nx serve new-tui-tasks-hanging
# Observe the Angular dev server prompting with the following message:
#   Port 4200 is already in use.
#  Would you like to use a different port? (Y/n)
```
