## Introduce

When you use `ls` on osx(Mac), you can see the ugly list like below.

<img src="https://i.imgur.com/bJ4Z0O0.png" width="50%"></img>

Try **pretty_ls_for_osx**.  
**pretty_ls_for_osx** provides list which is sorted and highlighted properly.

<img src="https://i.imgur.com/YczLtfx.png" width="50%"></img>

## How to use

Open your terminal and excute the commands below. Done :)

```
unalias ll
function ll() { ls -alp $@ | awk 'BEGIN{s =""; d= ""; f=""}{if($1 ~ /^d/)d = d $0 "\n"; else {if($9){if($1 ~ /^l/) f = f  "\033[36m" $0 "\n"; else if($1 ~/x/)  f = f  "\033[35m" $0 "\n"; else f = f "\033[0m" $0 "\n"; }else s= $0 } }END{print s; gsub(/\n$/,"",d); print "\033[32m"  d "\033[0m"; gsub(/\n$/,"",f); if(f!="") print "\033[37m" f "\033[0m";}';}
```
After that, when you excute `ll` in teminal, pretty list will be shown.
