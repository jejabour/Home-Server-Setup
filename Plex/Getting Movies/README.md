# Movies

This page is going to be dedicated to specifically getting the right Blu-ray drive, MakeMKV, and Handbrake.

1. [MakeMKV](#makemkv)
2. [The Blu-ray Drive](#the-blu-ray-drive)
3. [Handbrake](#handbrake)
4. [The Actual Process](#the-actual-process)

## MakeMKV

[MakeMKV](https://www.makemkv.com/) is, as far as I know, the only software that will actually rip movies from a disc, and do it in the actual quality uncompressed from the disc, and while it has a free version, it limits you to like 5 per month or something. 

#### Blu-ray drives that can rip

Only some blu-ray drives are actually capable of de-encrypting blu-ray discs to be able to rip them. The MakeMKV forums have a list of drives that are approved, because yes, there are approved ones that you have to jailbreak. The list is [here](https://forum.makemkv.com/forum/viewtopic.php?f=16&t=19634). That's right, you have to jailbreak your blu-ray drive to get it to do the de-encryption and rip blu-rays. 

By jailbreaking, I mean flashing a particular firmware that I don't remember being too hard to do. If I remember right, you just download the software, which is in the link above, and you have to run a particular command depending on the drive you have. [Here](https://youtu.be/jyQV1aPlbow?si=FNkSesXluLyeLQq_) is a youtube video where a guy walks through it.


## The Blu-ray Drive 

I ordered this [LG 4K UHD Blu-ray drive](https://www.amazon.com/gp/product/B079LTC6ML/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), but not all 4K and Blu-ray drives are made equally. Blu-ray actually has some encryptions built in that prevent users from ripping movies from them, because of course they do. If you just want to do DVD, then I believe any old drive will work, but who wants to just do DVDs? 


## Handbrake

Handbrake is technically a transcoding software. It does do video conversion, but it's also transcoding the "codec" behind the video, which is the form of compression being used.
The disc a movie is on will not use any compression whatsoever, and MakeMKV leaves it in that true raw uncompressed format, so it doesn't have any codecs on it.

The reason I bring Handbrake into the equation is because when you rip an uncompressed 4K movie, it's gonna be like 80Gb and some of us broke losers don't have infinite storage space. Handbrake will add a compression in the codec you want, and while that sounds like a bad thing, video compression codecs nowadays are really really really really advanced and really efficient to the point that when they're played back the video looks nearly identical but significantly reduces the file size.

It does, however, look a little complicated up front.

## The Actual Process

So how do you actually do everything once you've gotten your blu-ray drive, flashed the right firmware, bought MakeMKV, have a movie you want to rip, and downloaded Handbrake?

- MakeMKV
    - Start by opening MakeMKV and putting the disc in your drive. 
    - Click on the image of a disc drive once it's ready, and MakeMKV will read your disc and then present you with options. 
    - What you see here are likely the movie itself and all of it's bonus features, deleted scenes, stuff like that. 9 times out of 10, you can tell which one is actually the movie by the file size. The movie is the biggest one.
    - Fun fact, you can de-select everything on one level by right clicking.
    - If you open the dropdown on the main movie, usually you'll see movie in all of it's languages, sound profiles, and all the captions.
    - I highly recommend in this step to make sure you check the english subtitles. If you don't do it here and you want subtitles in Plex, you have to get them in a separate file some other way and it's a pain in the ass.
    - Once you've only checked what you want, and you're good with the file path on the right side (I usually rip to a different location than my Plex library), click the button next to the path to start ripping. This will take a while

Now you have your extra chonky movie file, I recommend you go ahead and change the name of the file to it's correct name and year. You can double check the source that Plex looks at by going to TVDB.com and looking up the movie. After that, you can run it through Handbrake. Optional, but it does save on file space with basically indistinguishable quality

- Handbrake
    - Open Handbrake and it will prompt you for sources. I recommend before dropping a movie in to go ahead and open Preferences > Output > and changing the output path to where your Plex Library looks so you don't have to do it for each movie.
    - Drag and drop your movies into Handbrake at this point
    - There are lots of opinions on the best settings within Handbrake, and it's gonna vary per source too (like DVD, Blu-ray, and 4k). You can make presets for each one too, which is what I did. Just do that as you come by them.
    - *Personally* I make all of my files output to .mkv format. I think it's the format that is both the most widespread usable and can have the option of subtitles on or off within the video, and multiple sound channels and all that.
    - I typically don't mess with Dimensions or Filters. I added some filters when I was digitizing old family VHS tapes to try and clean it up a little, but otherwise I leave them alone.
    - Video is probably the most important tab. I have a newer Nvidia GPU, and H.264 is usually the most go-to, but H.265 is just the next version, so I do H.265 NVENC. The slider on the right is very important too. Basically the further right, the higher quality but the longer it takes and the bigger the file I think. It seems a lot of people stick with around 20-18ish. I also set the framerate to Same as Source and Variable. I figure movies are gonna have a constant framerate anyway.
    - For audio, I don't entirely understand what I'm looking at, but I usually have two, one where I set it to surround sound and one for stereo.
    - Similar with subtitles. I always make sure there is a track for Forced English and English. Forced English is when subtitles come on for like when someone speaks in a different language or something, so I make sure that's there.
    - You don't have to do anything for Chapters and Tags. Or at least I don't
    - Once you've finished your settings, I recommend saving the preset.
    - Double check the file path on the bottom is where you want the file output.
    - Finally, you can now hit Add to Queue if you have more than one movie, or just Start Encode. This will take a while too, but once it finishes, you're done! You can open Plex and it should show up, if not, hit Scan Library in the three dots at the top next to your movie library header.



