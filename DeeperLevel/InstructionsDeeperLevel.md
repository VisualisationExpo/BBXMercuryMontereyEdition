## WELCOME TO BBX MERCURY FOR MACOS MONTEREY

![preview](https://i.ibb.co/YdbK3gP/preview.jpg?raw=true)

### THANK YOU! 😍 FOR DOWNLOADING THIS THEME ###

> I have been tinkering with this for quite some time and you downloading it gives me a warm feeling inside
> 
> It encourages me to create more themes, and expand on the content 
> 

**NEXT, I'LL DESCRIBE HOW TO INSTALL SYSTEM THEME FILES DIRECTLY ON THE SYSTEM**

# NOW FOR SOMETHING COMPLETELY DIFFERENT


## LET'S DO IT MANUALLY

**THIS IS A MORE INVOLVED AND I SUGGEST THAT YOU USE THIS -ONLY- IF YOU KNOW WHAT YOU'RE DOING.**

While booted to your Recovery Partition, type the following. Press the Enter-key after each command

`csrutil disable`

`csrutil authenticated-root disable`

Reboot

### Now that we're back to our regular user login.
Open `/Applications/Utilities/Terminal`

Type in the following. 
`mkdir ~/.SystemMount`

This one here will list your mounted drives. Something we need for our next steps: `mount`

Look at the list that comes up - then at the very top look for a line similar to this. It will be your system drive and that's what we're going to mount in a hidden folder inside your Home-folder

 `/dev/disk2s5s1 on / (apfs, sealed, local, read-only, journaled`

**Take note of the text** `disk2s5s1` 
However, your drive might instead be:

`disk3s5s1`

`disk5s5s1`

or even `disk3s1s1`

_This all depends on the amount of drives connected to your Mac_

_If you add any new drive, such as a USB key or external harddisk, then this will change, and you have to pay attention to the new disk-number_

### Do this next while in Terminal

**Eliminate the s1** from the e.g `disk2s5s1` string, and you're left with just `disk2s5`

Type in `sudo mount -o nobrowse -t apfs /dev/disk2s5 ~/.SystemMount`

> Leave the whole download in your ~/Downloads folder for the following to make any sense

>>Next is a bit tricky if you haven't used Terminal for much. Copy this whole string to your Terminal window

	sudo cp ~/Downloads/BBXMercuryMontereyEdition/DeeperLevel/THEMECAR/Aqua.car ~/.SystemMount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/ && sudo cp ~/Downloads/BBXMercuryMontereyEdition/DeeperLevel/THEMECAR/DarkAqua.car ~/.SystemMount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/ && sudo cp ~/Downloads/BBXMercuryMontereyEdition/DeeperLevel/THEMECAR/VibrantLight.car ~/.SystemMount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/ && sudo cp ~/Downloads/BBXMercuryMontereyEdition/DeeperLevel/THEMECAR/VibrantDark.car ~/.SystemMount/System/Library/CoreServices/SystemAppearance.bundle/Contents/Resources/

**(Warning will reboot your Mac almost right away)**

next you can lastly type in
`sudo bless --mount ~/.SystemMount/ --bootefi --create-snapshot && sudo reboot`