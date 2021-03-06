Github.js
=============

Ever wanted to store a file on Github right from the browser? Here you are.


Create a Github instance.

```js
var github = new Github({
  username: "YOU_USER",
  password: "YOUR_PASSWORD",
  auth: "basic"
});
```

Or if you prefer OAuth, it looks like this:

```js
var github = new Github({
  token: "OAUTH_TOKEN"
  auth: "oauth"
});
```

Expose API for a given repository.

```js
var repo = github.getRepo(reponame);
```

Retrieve all available branches (aka heads) of a repository.

```js
repo.listBranches(function(err, branches) {
  
});
```

Store contents at a certain path, where files that don't yet exist are created on the fly.

```js
repo.write('master', 'path/to/file', 'YOUR_NEW_CONTENTS', 'YOUR_COMMIT_MESSAGE', function(err) {
  
});
```

Not only can you can write files, you can of course read them.

```js
repo.read('master', 'path/to/file', function(err, data) {
  
});
```

Move a file from A to B.

```js
repo.move('master', 'path/to/file', 'path/to/new_file', function(err) {
  
});
```

Remove a file.

```js
repo.remove('master', 'path/to/file', function(err) {
  
});
```

Listing all files of a repository is easy too.

```js
repo.list('master', 'path/to/file', function(err, data) {
  
});
```