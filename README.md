# regionset - adjusts and shows the region code of DVD drives
Minor update of the linux regionset program copied from http://linvdr.org/projects/regionset.

Below is the original README from the web page with some minor edits as published by Mirko Doelle <cooper@linvdr.org>.

------

### What are region codes?

Video DVDs contain most often a region code flag indicating the geographical region where the DVD was published (enabling the film industry to control the distribution). There are eight region codes possible:

    "North America (USA and Canada)",                                                                         /*Region 1*/
    "Japan, Europe, South Africa, the Middle East (including Egypt) and Greenland",                           /*Region 2*/
    "Southeast Asia, and East Asia (including Hong Kong).",                                                   /*Region 3*/
    "Australia, New Zealand, the Pacific Islands, Central America, Mexico, South America, and the Caribbean", /*Region 4*/
    "Eastern Europe, Russia, the Indian Subcontinent, Africa, North Korea, and Mongolia",                     /*Region 5*/
    "China",                                                                                                  /*Region 6*/ 
    "Reserved for unspecified special use",                                                                   /*Region 7*/
    "Special international venues for air and oceanic travel"                                                 /*Region 8*/

On delivery, most DVD drives have no region code set. The drive firmware allows you to change the region code, but on nearly all drives you are limited to five (5) changes. After the fifth change, the DVD drive will stay fixed on that code -- on some drives you can upgrade the drive firmware and have then additional five changes, on other drives you won't be able to change the region code any more.

There are a couple of region code free DVDs on the market, but some drives will deny playing them without setting a region code for the drive first. After setting the region code, the drive will refuse playing any Video DVD (perhaps also Audio DVDs, I never had one to try out) with a different region code than its own.

If you set a DVD drive to region code 2 (RC2), you'll only be able to play region-code-2-DVDs from Europe, Middle East, South Africa and Japan -- the drive will definitively not play any US or Canadian DVD, nor Austrailian or Chinese. So if you cannot play a DVD because of the wrong region code, there is nothing the DVD player software can do about but changing the region code of the drive if you have any changes left.

So always be very very careful changing the region code, it could be your last try before you're forced to buy a new drive (or play foreign DVDs forever).

### Installation

Just unpack the package then call "make". After compiling, you'll find the binary "regionset" in the directory which you should copy to /usr/sbin (as root, of course)

### How to use the programm

You need write access to the DVD drive, either by group or by being root. There usually must be a readable Data CD or Data/Video DVD in the drive -- it does not matter if it's your favorite Windows CD, a video or a DVD with your last backup.

By default, regionset will use /dev/dvd to find your DVD drive. You can adjust this by entering the path to the DVD device as first command line parameter (please absolute path!).

If everything goes well, regionset will show you the current region code of the drive, how often it has been changed and how many changes are left. If there are any changes left, it asks for the new region code (see table above). After confirmation, the new region code will be set -- if you enter the same region code as the current one of the drive or just break the programm, regionset will just exit without setting the new code. On successful change of the region code, you'll get a confirmation.

### The Credits

regioncode.c was written by Christian Wolff <scarabaeus@convergence.de> from Convergence and published as part of the package dvd_disc_20000215.tar.gz on the Convergence homepage. Due to changes of the german copyright law, the package was removed because it had some relations to CSS and copying DVDs.

There were no mirrors (at least none I could find), so I decided to pack regionset.c and a CSS free version of the UDF functions together and redistribute it. Oh, I added some outputs, nothing to speak of, and rated the whole thing as version 0.1. I plan to add some command line arguments to make regionset more scripting-friendly in later versions.



