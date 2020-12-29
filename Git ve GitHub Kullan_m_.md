# Git Komutlarim

Make one commit per logical changes, not for every line or too long periods.

Branch degistirme `git checkout branch_name`

Add all files to commit `git add .`

Push `git push origin branch_name`

Rebasing local commits `git rebase --interactive HEAD~7`

Linux ve MacOS 'da iki dosya arasındaki farklıları gösterme komutu `diff -u` 

## Kullanmaktan kacinilmasi gereken komutlar

Git ile bir dosyayi kalici olarak silme (gecmis de dahil) `git filter-branch --index-filter "git rm -rf --cached --ignore-unmatch FILE-PATH" HEAD`.

## Git'in command line'ı renklendirme ayarı

```
git config --global core.editor "'/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl' -n -w"
git config --global push.default upstream
git config --global merge.conflictstyle diff3
```
