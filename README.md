# build-commit
 Commit built files without polluting git

build-commit is a CLI app which is able to build your package, commit the build files, and do this without polluting git.

## Installation
To use it from shell install it globally:
```
npm install build-commit -g
```

To only use it for one package
```
npm install build-commit --save-dev
```

### Usage
The basic usage is to add the following to your `scripts` entry of your `package.json`:
```
"build-commit": "build-commit -o dist",
```
Which builds the package (using `npm run build` by default), and adds `dist` folder to your repository. You can run this using:
```
npm run build-commit
```

For more options see the next section.

### Options
```
>> build-commit --help

Usage: build-commit [options]

Options:
  -V, --version                   output the version number
  -d, --directory <directory>     Root of the git directory (default: ".")
  -o, --output <directory>        Build destination folder (default: "dist")
  -m --message <message>          If provided does not run post-command (default: "chore: add built files")
  -pre, --precommand <command>    Execute a shell command before committing. (default: "npm run build")
  -post, --postcommand <command>  Execute a shell command after committing.
  --nopre                         If provided does not run pre-command
  --nopost                        If provided does not run post-command
  -h, --help                      display help for command

```
