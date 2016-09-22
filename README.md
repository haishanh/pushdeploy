# Push to deploy

This is just a dumb bash script wrapped like a npm package, but not a single `*.js` included. It can be used to push content in a directory to a given branch of a remote git repository.

## Install

```sh
npm install -save pushdeploy
```

## Usage

in your `package.json`:

```sh
"scripts": {
  "deploy": "deploy -d dist -r git@github.com/abc/xyz.git -b gh-pages"
}
```

run `npm run deploy` to deploy.

## More

Here is the result of `deploy -h`:

```sh
Usage:

  deploy.sh -d DIR [-r REMOTE] [-b BRANCH] -h

  Push contents in DIR to branch BRANCH of repository REMOTE

    -d DIR
        Specify the directory
        where files in it will be deployed

    -r REMOTE
        Specify the remote repository
        If omitted, deploy.sh will try to guess
        from the remote info of current local repo

    -b BRANCH
        Specify the remote branch
        If omitted, deploy.sh will use "gh-pages" if
        if present in current local repo

    -h
        Show this help message

Examples:

  deploy.sh -d dist -r origin -b gh-pages
  deploy.sh -d dist -r git@github.com:abc/xyz.git -b gh-pages
  deploy.sh -d dist -b gh-pages
```
