# ZSH 自带GIT快捷键

|Alias|Command|
|:---:|:------:|
|gapa|	git add --patch|
|gc!|	git commit -v --amend
|gcl|	git clone --recursive
|gclean|	git reset --hard && git clean -dfx
|gcm|	git checkout master
|gcmsg|	git commit -m
|gco|	git checkout
|gd|	git diff
|gdca|	git diff --cached
|glola|	git log --graph --pretty = format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --all
|gp|	git push
|grbc|	git rebase --continue
|gst|	git status
|gup|	git pull --rebase
|gwip|	git add -A; git rm $(git ls-files --deleted) 2> /dev/null; git commit -m "--wip--"