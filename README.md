# Ubuntu_mplayer_PNG-read-error
when it is the first time seeing the error with start mplayer,

    "Error in skin config file at line 6: PNG read error in /usr/share/mplayer/skins/default/main".


## how to fix  
CTRL+ALT, open temrinal  
copy following and paste, build/run the script,  
```
## install "perl" package
sudo apt-get install perl

## install "convert" package
sudo apt install iamgemagick


## build the script first
sudo tee -a fix.sh > /dev/null <<EOT

#!/bin/bash
cd /usr/share/mplayer/skins/default
for FILE in *.png 
do 
    sudo convert $FILE -define png:format=png24 $FILE 
done
EOT

## give the script executeable
sudo chmod +x fix.sh

## run the scrip
sudo ./fix.sh

## job done

```
