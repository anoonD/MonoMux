# MonoMux

A (hopefully) helpful bash script to merge your Monogatari video files
with commentary audio+subs

## Requirements

To merge the files, you need `mkvmerge` installed on your computer.
On Arch Linux you can install this with `pacman -S mkvtoolnix-cli`.
Unsure what the instillation process is on other Linux distros or MacOS.

This script also uses `seq`, which while ubiquitous is not POSIX, so I
may as well mention it.

## Configuration

Configure MonoMux by editing the `env` file:

* `anime_dir` should be the directory where your Monogatari .mkv files are stored
* `audio_dir` should be where the commentary audio .mp3 files are stored
* `subs_dir` should be where the commentary subtitle .ass files are stored

Also, your file names should all include the episode numbers, formatted
with proceeding "Ep" and leading zeroes:

* "Bakemonogatari Ep03 [BD 1080p]".mkv is __okay__
* "Owarimonogatari SSEp14.mp3" is __okay__
* "Nisemonogatari 10.ass" is __NOT okay__
* "Tsukimononogatari Ep3.mkv" is __NOT okay__

## Usage

To merge commentary files for Bakemonogatari, run

```
./commentize Bakemonogatari
```

Then, assuming that

* All your files are properly named
* The directory $anime_dir/Bakemonogatari exists and contains your .mkv files
* The directory $audio_dir/Bakemonogatari exists and contains your .mp3 files
* The directory $subs_dir/Bakemonogatari exists and contains your .ass files

Then MonoMux should (probably) successfully generate merged .mkv files!
