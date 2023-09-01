<h1 align="center">
  🎶 NBS Converter for Music Machine 🎶
</h1>

This repo contains some Python scripts to convert `.nbs` files into a schematic that can be pasted into your Minecraft world. This is specifically designed to work with jazziiRed and Mooncatcher's Music Machine, featured in [this YouTube video](https://www.youtube.com/@jazziiRed) and downloadable [here](https://www.google.com/). Basically, it can take any `.nbs` song and translate it into several sequences of music discs stored inside chests, so you an enjoy any song you want in our machine!

***Disclaimer**: This is not the most professional code in the world, as most of it was written by me on a plane. You will need a basic understanding of how to run Python scripts using the command line, but don't worry, I will provide you with resources in the below sections.*

***Note: I will not be proactively updating this code unless I feel the need to. I will also not provide any tech support to those of you who are having techical troubles with Python. This is nothing against you, I just don't have the bandwidth. Hopefully the resources I provide will be enough to guide you through any technical issues you have.***

## Getting Started

### Installing Open NBS Studio

Let's start off with installing [Open NBS Studio](https://opennbs.org/), the program used to create, edit, and listen to `.nbs` songs. This is optional, but it'll help a lot when it comes to previewing your songs before and after formatting to make sure that they'll sound good in the machine.

***Note**: This program does not currently work with MacOS. Sorry Mac users... The good news is that the scripts will still work on your Mac - you just won't be able to preview your songs before importing them into the game.*

### Installing Python

Now for the technical stuff. First off, you need to have Python installed on your computer in order to run these sripts. If you've never done this, simply go to the [Python download page](https://www.python.org/downloads/) and install the latest version of Python for your operating system. If you are on MacOS, you may also use [Homebrew](https://brew.sh/).

Whatever operating system you have and whatever method you choose, just make sure that Python installed properly by running one of the following in your Command Prompt (Windows) or Terminal (MacOS or Linux):

```bash
py --version
python --version
python3 --version
```

This should spit out the version of Python that was installed on your system.

***Note**: `python3` can be replaced with whatever major version of Python you just installed, ie. `python2` or `python4`, if you're from the future.*

If none of these commands work, Google your error message. There are plenty of online forums such as stackoverflow that may contain the answer to your issues. Failing everything, simply uninstall and reinstall Python. Sometimes that works.

Once one of these commands work, take note of which one (`py`, `pythoh`, or `python3`) worked on your system. This will be the command used to run Python scripts moving forward.

### Installing Packages

The two Python scripts in this repo make use of two existing Python libraries: [pynbs](https://github.com/OpenNBS/pynbs) and [mcschematic](https://github.com/Sloimayyy/mcschematic). The first is used to parse, edit, and create `.nbs` files, and the second is used to create and edit Minecraft schematics. Go to their respective Github repos for instructions on how to install.

Both of these libraries can be installed using `pip`, which should be automatically installed for you alongside Python. If you have issues with `pip`, please look up your error message. You might need to use `pip3` (or whatever version). Just like with Python, you can check your version of `pip` using either of the following commands:

```bash
pip --version
pip3 --version
```

Once you have these installed, the hard part is over! 🎉

Now for the fun part...

## Running the Scripts

So in order to run the scripts, you need to have them on your computer. You can either clone this repository using git, or you can simply download the following three files and put them all in the same folder.

- `constants.py`
- `nbs_format_song.py`
- `nbs_generate_schematic.py`

Once you've done this, you're ready to convert any `.nbs` song you wish! Download or compose any song you like (I have some good ones in the `example_songs` folder.), and drop them into the same folder as the three `.py` files.

### Formatting the Song

The first thing that you will want to do is format your song. However you decide to build the final configuration of the music machine, it will not be able to play every `.nbs` song as is, due to chord size limitations, length, illegal notes, etc. So this first script is designed to format the `.nbs` song so that our machine can actually play it.

But before you run the script, you might want to tweak some settings. To do so, open `constants.py` in the text editor of your choice (even notepad is fine) and take a look at any of the variables marked with `EDITABLE SETTING`. **DO NOT** edit any of the variables marked with `DO NOT EDIT` (unless you want to, I'm not your mom).

FYI - If you're just using this script for the machine in the world download, all the default settings will work fine. In fact, I would advise against editing this file if this is the case.

Once you've made the edits that you want, make sure to save the file. Now it's time to actually run the script!

#### Running the Formatting Script

First, navigate to the folder that your scripts are stored in using either Command Prompt (Windows) or Terminal (MacOS or Linux). Once there, run the following command:

```bash
py nbs_format_song.py
```

or whatever Python command worked for you in [Installing Python](#installing-python).

Follow the instructions that the script gives you, and at the end it should spit out a brand new `.nbs` file that's correctly formatted! Take a listen to this to see if it still sounds good, and once you're satsified, it's time to move on to the next step!

### Generating the Schematic

Now that you have a formatted `.nbs` song that sounds great, it's time to transform it into a form that can be pasted into Minecraft!

This part's really easy. Again using either Command Prompt or Terminal, run the following:

```bash
py nbs_generate_schematic.py
```

or whatever Python command worked for you in [Installing Python](#installing-python).

Follow the instructions that the script gives you, and at the end it should spit out a brand new `.schem` file that you can paste into your world!

## Pasting the Song into Minecraft

Ok, full transparency - this part requires you to have worldedit or some other mod that can handle `.schem` files in Minecraft. I'm not going to get into how to install this, as there are several great tutorials out there for installing and using worldedit. I'll link a couple here, but feel free to look around to find one that makes sense to you.

- [Installing Fabric](https://shockbyte.com/billing/knowledgebase/213/How-to-Install-Fabric-Mods-on-Your-PC.html)
- [Basic worldedit tutorial by BodhiMC](https://youtu.be/5PoHeqvxeos?si=Qo_AvVJ9Ppb2OLve)
- [Schematic tutorial by Avomance](https://youtu.be/P_mR4Y0R0uc?si=j1jXinxHueqxKS9W)

Once you're ready, simply load up the world. If you're using the world download, follow the instructions on the signs for exactly where to paste the song. The song will paste into your world as a straight row of chests labelled with signs.

***Note**: You will probably also want to download and use the `Silent_Discs` resource pack in this repo. This replaces all the music disc songs with silence, so you can only hear the note blocks while the machine is running. It's pretty obnoxious without it.*

Then, all you have to do is start it up and enjoy the music! 🎧🎶