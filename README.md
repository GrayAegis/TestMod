# Starsector Mod Template

This is a basic Github template to create a working Starsector mod.
Under the hood it uses a Gradle automation tool to fetch dependencies and compile source code.

## Usage

1. Have Java SDK installed, anything 7 or above will work
1. Pick a mod name (can have spaces, e.g. "My Starsector Mod") and mod identifier (cannot have spaces, only A-z, "mymod", try to make it unique across mod-verse)
1. Click "Use this template", use your mod identifier as "Repository name"
1. Run `./gradlew build` or `gradlew.bat` (depending on your operating system) - you will get "empty" jar file (empty because there is no code yet)

## Adding scripts

There exists a false notion that a mod needs to follow folder structure of the game, but this is only true for `data` folder.
In `src` folder the mod author is the king. As such you should structure your mod in a way that makes it easier for you to code.
Even in `graphics` folder you can do whatever you want, as long as correct references are used in `data` and `src`.

Whether you go deep (like Starsector, many nested folders) or broad (and shallow-ish, many folders on same level, not many subfolders) is up to you.
However you decided to go, you also need to decide whether to [package by feature or by layer](http://www.javapractices.com/topic/TopicAction.do?Id=205).
If all of that is too confusing, simply follow Starsector's structure.

To start your mod:
1. Create a folder in `src/main` with the mod identifier name (e.g. `src/main/mymod`).
1. (Optional) Add your mod plugin, recommended would be `src/main/mymod/MymodPlugin.java` - this file "lives" in `package mymod;` and initializes your mod.
1. Write remaining code.
1. Build, package, release.

## Building

Already covered in usage, just run `./gradlew build` or `gradlew.bat build`.

## Packaging

1. Create `mod_info.json` with correct structure.
1. Make a (temporary) folder and copy the following:
   1. `data` and `graphics` folders (if any),
   1. jar file generated by Gradle, and
   1. any other files you want to bundle.
1. Create a zip file of that folder.

## Releasing

1. Click "Create a release" (either from main page of your repository or from "Releases" tab).
1. Name a tag, add title, and add description (optional, usually a list of changes made in this version).
1. Add zip file you created in packaging and click "Publish release".
