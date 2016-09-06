# ZSH_EVAL_CONTEXT

In zsh the `$ZSH_EVAL_CONTEXT` array can be used to figure out the context of your code.

I use it in the `chpwd()` hook in order to show a listing of directories I cd
into *only* in the context of the interactive shell. That way I avoid to call
ls in contexts such as calling `cd` in a custom function.

Here is my `chpwd()` hook code:

```sh
# Auto ls when cd
function chpwd() {
    # Make sure we are not in anything else than in shell/chpwd.
    [[ $ZSH_EVAL_CONTEXT == "toplevel:shfunc"  ]] || return
    emulate -L zsh
    ls --color=auto --group-directories-first
}
```

You can learn more details about it in the zshparam(1) man page.
