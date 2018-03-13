# node-add-module
Example node.js module, travis-ci, npm

## Set up
### Login to npm
```bash
npm login
```
### Initialize npm package
```bash
npm init --scope=username
```
Or
```bash
npm init --scope=orgname
```
### Npm authentication
#### Token
When you log into npm via the Command Line Interface (CLI), a token is created and given to your computer.  It is stored in your .npmrc file. 

Open the .npmrc file, e.g. **C:\Users\username\.npmrc**

And copy the auth token contained within this file, e.g.:
**//registry.npmjs.org/:_authToken=103af1f1-f5a2-37e6-b1c9-a35b17d5fe34**

#### Travis-CI

Login to Travis-CI - https://travis-ci.org
1. Enable builds for the repository by clicking the checkbox
2. Click on the repository -> More Options -> Settings
3. Add two new environment variables:
    * NPM_AUTH_TOKEN - the npm auth token
    * NPM_EMAIL - the email address to associate with this package


### Bump package version, tag, commit and push module to GitHub
```bash
npm version patch|minor|major –m “Version %s - version bump message”
```
**%s** = the new version number.

This command will bump the version number in **package.json**, add a new commit, and tag it with this release number.

**Note:** Your Git working directory has to be **clean** before you can run **npm version**.

```bash
git push origin master --tags
```
### Troubleshooting
#### Make scoped npm packages public
npm assumes that scoped packages are private by default. You can explicitly tell npm your package is a public package and avoid this error by adding the following to your **package.json** file

```javascript
"publishConfig": {
  "access": "public"
}
```

## References and useful links
* https://docs.travis-ci.com/user/deployment/npm/
* https://docs.travis-ci.com/user/build-stages/deploy-npm/ 
* https://codeburst.io/how-to-create-and-publish-your-first-node-js-module-444e7585b738
