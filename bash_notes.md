# Bash Notes

This is a collection of bash notes.

## Move Cursor

* `Ctrl + ->`, `Ctrl + <-`, `Alt+b`, `Alt+f` Move by word
* `Ctrl + a` / `Ctrl + e` Move to beginning / Move to end
* `Ctrl + ] + [letter]` Find forward
* `Ctrl + Alt + ] + [letter]` Find backward

## Editing Text

* `Ctrl + T` Move a char to left

## Kill Text

* `Alt + Backspace`, `Ctrl + w` word
* `Alt + d` current to space
* `Ctrl + k` current to end of line
* `Ctrl + u` current to home
* `Ctrl + y` paste the deleted text
* `Alt + y` paste the history of deleted text

## Finding

* `find . -type f -name "*~" -exec rm -f {} \;` Remove all matched files under a directory by matching/searching 
* `grep -lr -e --exclude-dir=log --exclude=tags 'old_text' * | xargs sed -i 's/old_text/new_text/g'` Find and replace text in all files under a directory

## Process
* `ps aux`
* `lsof -i :<port>` / `netstat -tlnp | grep <port>` Looking for the process listening on port
* `ls -lta .` Opend files list

## History

* `!$` Last command parameter
* `cd -` Go to last directory
* `Ctrl + r` reverse search history, press Enter to exec or `Ctrl + e` to place in command
* `![command]` reverse search the last matched command to exec
* `Alt + .` place word history in command
* `^[chars]` remove chars and exec last command
* `^[old]^[new]` replace chars and exec last command

## Sed

* `sed 's/<oldstring>/<newstri ng>/g'` Replace string in a file
* `sed -i '1i\Your text go here' /etc/hosts` Add first line to text file

## Zip & Unzip

* `tar -jxvf filename.tar.bz2` To extract a tar.bz2 file
* `tar -zxvf filename.tar.gz` To extract a tar.gz file

## Free up Memory

* `sudo sync; echo 3 | sudo tee /proc/sys/vm/drop_caches > /dev/null`

## Download or Upload File/Directory
* `scp user@mydomain.com:~/myfile ~/myfile` Download file
* `scp -r user@mydomain.com:~/mydir ~/` Download directory
* `scp myfile user@mydomain.com:~/myfile` Upload file
* `scp -r ~/mydir user@mydomain.com:~/` Upload directory

## SSH
* `cat ~/.ssh/id_rsa.pub | ssh root@example.com 'cat - >> ~/.ssh/authorized_keys'`
