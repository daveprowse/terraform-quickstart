# Lab 02 - Augmenting Terraform and the Help System

## Install Terraform autocomplete

- First, make sure that you have an existing .bashrc or .zshrc file. 
  
  If not, create one, for example:

    `touch ~/.bashrc`

- Install autocomplete:

  `terraform -install-autocomplete`

- Restart the shell

> Note: This is very helpful for Bash, but not quite as necessary for Fish or ZSH

## (Optional) Install a VSCode Terraform extension

This can be done directly within VSCode or from one of the following:

- Official Hashicorp extension:

  https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform

- Anton Kulikov extension:

  https://marketplace.visualstudio.com/items?itemName=4ops.terraform

## Examine the help system

First, analyze the main help command:

`terraform -help`

You could also type the following options: 

`terraform --help`, `terraform -h`, or `terraform --h`

Take note of the main commands including: init, plan, validate, apply, and destroy.

Now, learn more about a subcommand. 

  For example: 
  
  `terraform -h init`

  You could also type: `terraform init -h` if you wish.

> Note: 🧠 Spend some free time learning the help system! This, and the [HashiCorp Documentation](https://developer.hashicorp.com/terraform/docs) are the best ways to get over the learning curve for Terraform.

---

## (Optional) Configure Vim

If you use Vim, you might want to consider the following:

### Syntax Highlighting With Vim Polyglot:

Without some type of syntax highlighting, file displayed in Vim will simply be all white text. This can be stressful on the eyes. 

One way to alleviate this is to use vim-polyglot.
vim-polyglot: https://github.com/sheerun/vim-polyglot

It requires Vim Plug:

https://github.com/junegunn/vim-plug

So we will need to install plug, install vim-polyglot, and configure it for Vim.

> Note: The directions below assume that Vim has not been configured at all. If you already have Vim configured. you may not need all of the directions listed.

1. Install Plug
https://github.com/junegunn/vim-plug
```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

2. Install vim-polyglot by modifying .vimrc

If you don't have a .vimrc file, create one in your home directory:

```bash
set nocompatible

call plug#begin()

Plug 'sheerun/vim-polyglot'

call plug#end()
```

3. Install the plugin within Vim
`:PlugInstall vim-polyglot`

4. Reload the .vimrc file
`:vs ~/.vimrc`

### Syntax Highlighting With HashiVim:
https://github.com/hashivim

For example, vim-vaultproject or vim-hashicorp-tools (which has multiple HashiVim tools combined)

You can install these as typical Vim packages or with vim-pathogen: https://github.com/tpope/vim-pathogen

### More Vim modifications

You might also wish to add the following to your .vimrc file:

`set number` adds line numbers to files opened with Vim.

`:color <colorscheme>` replace colorscheme with your favorite color, for example: desert, ron, zellner, etc. For a list of colorschemes, do the following:

In Vim, type `:color` then <kbd>Space</kbd> followed by <kbd>Ctrl+D</kdb>