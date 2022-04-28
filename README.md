## Russian-language Keyboard Layout with White Red White Belarus Flag ##

### Верым Можам Пераможам! / Слава Україні! ###

Inspired by https://github.com/palmerc and his Ukrainian flag https://github.com/palmerc/Ukrainian-Russian


![Input Sources Menu](https://i.imgur.com/tUGvHoS.jpg)

For those Belarusians who are tired of staring at a Russian flag while working on Mac with Russian keyboard


Just copy the `.keylayout` and `.icns` files into the folder `~/Library/Keyboard Layouts/` 
Then Open Keyboard Preferences and add plus button on Input Sources tab.
There might be reboot required

    git clone https://github.com/igorekb/True-Belarusian-Russian
    cd True-Belarusian-Russian/
    sudo cp Belarusian\ \(Russian\).* ~/Library/Keyboard\ Layouts/

### Modify the layout ###

Feel the need to update the layout to your liking by adding in the Ukrainian language characters? Download the keyboard layout tool [Ukelele][0] and have at it.

[0]: http://scripts.sil.org/ukelele


### Choose Your Own Flag ###

Find a png of the flag. Make sure the png size is squared (1024/1024) and the flag dimensions are correct

    input_filepath="flag.png" 
    output_iconset_name="CFE.iconset"
    mkdir $output_iconset_name


    sips -z 16 16     $input_filepath --out "${output_iconset_name}/icon_16x16.png"
    sips -z 32 32     $input_filepath --out "${output_iconset_name}/icon_16x16@2x.png"
    sips -z 32 32     $input_filepath --out "${output_iconset_name}/icon_32x32.png"
    sips -z 64 64     $input_filepath --out "${output_iconset_name}/icon_32x32@2x.png"
    sips -z 128 128   $input_filepath --out "${output_iconset_name}/icon_128x128.png"
    sips -z 256 256   $input_filepath --out "${output_iconset_name}/icon_128x128@2x.png"
    sips -z 256 256   $input_filepath --out "${output_iconset_name}/icon_256x256.png"
    sips -z 512 512   $input_filepath --out "${output_iconset_name}/icon_256x256@2x.png"
    sips -z 512 512   $input_filepath --out "${output_iconset_name}/icon_512x512.png"

    iconutil -c icns $output_iconset_name
    rm -R $output_iconset_name

    mv CFE.icns "Belarusian (Russian).icns"