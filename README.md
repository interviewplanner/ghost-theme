# ghost-theme
[Ghost](https://ghost.org) theme for the InterviewPlanner blog

## Development

### Requirements
- Node v10.19.0
- yarn

### First-time setup

The first time you clone this repo, you will need to set up a few things with the following command.
```sh
$ yarn
$ yarn setup
```
This performs a local installation of Ghost. It also links your `package.json` into your theme directory, and links your theme directory into your `ghost/content/themes` directory, so that you can preview your theme locally.

### Developing

1. Start Ghost.
```sh
$ yarn start
```

2. Navigate to `http://localhost:2368/ghost/` and set up your blog (e.g. create an account, name your blog, etc).

3. In `http://localhost:2368/ghost/#/settings/design`, scroll to the bottom and activate the `interviewplanner` theme.

4. As you make changes to the theme, you can see them on your local Ghost blog. If you aren't seeing your changes, it may be because of Ghost caching your styles. You can do a hard refresh (<kbd>Shift</kbd>+<kbd>Cmd</kbd>+<kbd>R</kbd> on Chrome on Mac) to see them.

### Deploying
1. Merge PR to `master`.

2. Get `master` up-to-date on your local machine.
```sh
$ git checkout master
$ git rebase master
```

3. Create the bundle.
```sh
$ yarn release:patch # or release:minor or release:major
$ yarn bundle
```

4. Go to the [staging blog settings](https://staging.interviewplanner.com/blog/ghost/#/settings/design) and upload the bundle.

5. If everything looks good in staging, go to the [production blog settings](https://interviewplanner.com/blog/ghost/#/settings/design) and upload the bundle.
