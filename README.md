# iTunesSync
Easy iTunes playlist syncing for Tesla USB flash drive
Highlights of the script:
- This script is for anyone that uses playlists for listening- not genre, album, artist, etc. as there are multiple copies of a song on the flash drive.
- Syncs (selectively) multiple playlists from iTunes to a drive/folder of your choice (including USB flash drive)
- Adds and deletes files automatically to reflect your current iTunes playlist setup in an iTunes playlist folder named Tesla (can be changed in the script)
- Changes the song genre to reflect the iTunes playlist for the copied file. The iTunes file retains it's current genre setting
- Play your playlist by selecting Genre in the Media Player of the Tesla
- Automatically converts Apple Lossless files to flac (using XLD's command line interface)

Details:
I've assembled an AppleScript that will sync a folder of iTunes playlists to a USB flash drive or a folder on your Mac. (No windows version  as I've used AppleScript for this.) You define a folder in iTunes (the default is Tesla) and add any playlists to it that you would like to sync. The script will copy all of the songs to your destination drive/folder and rename the genre of the song to the playlist. Using the media player in the Tesla, you can then select genre which will reflect your playlists in iTunes. (The genre of the iTunes song is temporarily changed when the file is copied but then changed back to the original genre.) If you have Apple Lossless files, you'll need to install both XLD and the command line script xld (included with the package) and the script will automatically convert the files to the flac format, playable in the Tesla. (You may need to make the xld script executable to work.)

Instructions:

1- Copy the script to the location of your choice on your Mac.

2- Install XLD on your Mac and install the command line tool (in CLI) from http://sourceforge.net/projects/xld/...atest/download

3- Install the command line interface "xld" (located in the CLI folder) in your applications folder. You made need to make it executable using terminal and chmod. To do this, open terminal, type cd /Applications, type sudo chmod 755 xld. Enter your system password and press enter.

4- Create a playlist folder in iTunes named Tesla and drag any playlists you'd like to sync to this folder. (You can change the default folder in the script if you'd like.)

5- Run the script (link below).

6- Choose your destination disk/folder.

7- Wait. If you have a lot of songs, it can take a long time. Hours. Particularly when copying to a USB flash drive.

8- Caution: the script does not check for adequate disk space. And since it makes multiple copies of the same file per playlist, it can use quite a bit of disk space. I'm not certain what would happen if a flash disk ran out of space. 

Notes:
- I'd initially choose a small playlist to test the setup. And sync to a folder on the desktop for testing. Better yet, make a copy of your iTunes folder, open the backup (using the Option key when clicking on iTunes and then select the backup). Note you'll have to change it back once done testing.
- Although the initial sync can take a while, future syncs will go much more quickly when only small changes have been made. The script will add and delete files to your destination based on your current playlists in the "Tesla" folder in iTunes.
- Your will end up with duplicate files on the destination drive/folder. Each song is copied from the playlist and the genre named to the playlist. This means that if a song appears in 5 synced playlists you'll have 5 copies of the song.
- If you initially sync to a folder on your hard disk, you can copy the folder to the USB drive. Next time, sync to the flash drive directly. It's a little less error prone due to timeouts or slow USB drives.
- The progress meter and counts are sometimes a bit wonky. They may or may not represent what is actually happening exactly... just sorta.
- The script makes a temp playlist called ZZ-Temp (get it?) and copies all of the playlist files to it. This playlist is not deleted at script end so that you can use it as a proxy to see how many files there are. This can be compared to the destination folder. The playlist folder is deleted on the next run of the script and then re-created with the designated playlists in the Tesla folder.  It is safe to delete this playlist and it will be recreated the next time the script is run.
- I've had timeout errors that I can't diagnose (maybe Time Machine locking files, other apps, etc.). If the final dialogue box reports errors or their is a discrepancy between the ZZ-Temp playlist and the number of files in your destination folder, just run the script again. If it the issue is a timeout, then usually second time is a charm!
- The only risk to your iTunes library is that the genre is changed momentarily when copying the file to the destination folder. If the script were to crash, there is a possibility that the iTunes song would be left with the playlist as genre vs. your original designation. 
- You can save the script as an application bundle, which will allow it to run directly without opening up the script editor.

Please make certain that you have a backup of your iTunes folder when you first start using this script. I have tested it on my Mac and laptop which are running Yosemite and the latest iTunes 12.1.0.50 as of March 5, 2015. The progress bar will break the script in earlier versions of OS X... 

This script makes syncing a USB flash drive almost as easy as syncing an iPod. Which is nice...

Please provide any feedback or if there are any AppleScript gurus out there, suggestions on how to improve it.
