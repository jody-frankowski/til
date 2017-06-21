# Global Gitignore

With Git you can configure a global gitignore, which is very helpful as you
don't need to rely on the projects' gitignores.

You just need to add the following lines in your `~/.gitconfig`, along with you
new `~/.gitignore`:

```
[core]
        excludesfile = /home/me/.gitignore
```
