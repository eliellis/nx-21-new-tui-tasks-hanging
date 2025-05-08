# Nx 21 Angular Dev Server Hangs After TUI Exit Reproduction

## To reproduce the issue

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

After assessing the above, it can additionally be observed that the issue _does not_ occur with other executors / continuous tasks, such as serving a Node application.
Doing the same as above, with the example Node application contained in this repository, will _not_ result in the same "hanging" behavior:

```shell
npx nx serve test-node-app
# After exiting the TUI, either by pressing Ctrl+C or 'q', the child process WILL exit.
# Running the same command again will NOT error out, as the port has been freed up:
npx nx serve test-node-app
```
