Show hidden files : CMD+fn+MAJ+; to display hiddenf file on Azerty/MAC OS
Unzip tar.gz file : tar -xzvf archive.tar.gz 
Open zip with password : `brew install p7zip` pour installer, puis `7za e archive.7z`

Export .mov from quicktime to gif : 
ffmpeg -i path_to_mov.mov -s 600x400 -pix_fmt rgb24 -r 25 -f gif - | gifsicle --optimize=3 --delay=3 > out.gif
https://gist.github.com/dergachev/4627207

ffmpeg -i path_to_mov.mov -f gif - | gifsicle --optimize=3 --delay=3 > out.gif
