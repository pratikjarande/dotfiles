#### How to clone and use ?
```
cd $HOME
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles clone --bare git@github.com:pratikjarande/dotfiles.git $HOME/.dotfiles
dotfiles config --local status.showUntrackedFiles no
dotfiles config core.sparsecheckout true
```

#### How to checkout only required files ?
```
echo ".vimrc" >> $HOME/.dotfiles/info/sparse-checkout
dotfiles read-tree -mu HEAD
```

#### Starting from scratch
```
git init --bare $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles config --local status.showUntrackedFiles no
dotfiles add <file>
dotfiles commit -m "<message>"
dotfiles remote add origin git@github.com:USERNAME/REPOSITORY/dotfiles.git
dotfiles push -u origin master
```
