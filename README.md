# Average4k Wiki (Current Version: b11.2.3)

Average4K information, all in one place.

WE LOVE KADE DEV HAHAHAHAHAHAH

**NOTE: All information stored is in the [Wiki tab](https://github.com/WizardMantis441/a4k-docs/wiki).**

*When looking at code samples, remember that your lua file must still be named `mod.lua`, and that you cannot have more than one lua file.*

If you want a good source on how to learn lua, here's the [Official Lua Documentation](https://www.lua.org/manual) website.

For people who aren't currently beta testers, [wishlist the game](https://store.steampowered.com/app/1828580/Average4k)!

Check out the current progress on the [Trello Page](https://trello.com/b/2CVDM9k9/average4k-trello)!

Join the [Discord Server](https://discord.gg/kadedev) for better announcements from Kade himself!

## Contributors
These are all the people who have worked on this document, helping by adding information:

```
Burger Gaming (Mods)
tylersfoot (Skinning)
```

If you want to become a contributor, either by making a code-sample you deem useful, or by adding information to the wiki, make a [pull request](https://github.com/WizardMantis441/a4k-docs/pulls)!


# Making a Modchart

Create the modchart by going into the chart's folder, adding a folder called mod, and putting mod.lua in the folder.

## Template
```
function create()

end

function update()

end
```

# Importing Songs And Packs

Do you have a song, and you have a chart, but you don't know where to put it? It's pretty easy to do so. This page is dedicated to the process of doing such.

## Step 1 - Making Folders

Go to the Average4k directory by right clicking on the game and clicking `Manage`. After that, click `Browse local files`.

![image](https://i.imgur.com/u6aMwZp.png)

You should now be in the game's directory. Click on the folder labeled `assets`, and then `charts`. Make a new folder, you can name it anything you want.

![image](https://i.imgur.com/916Iy8H.png)

For each song in your pack, make another folder inside of it and put your chart in that folder.

![image](https://i.imgur.com/tizrixd.png)

## Step 2 - Setting Up the Pack/Song.

Go back to the main pack folder you made and make a file called `pack.meta`.

![image](https://i.imgur.com/FL9m2Yt.png)

Open the file in a text editor of your choice, and put in the following code:
```
packName: [Insert your own pack name]
```

There are two optional parameters to your song/pack.

`showName` - Hides the pack name on the pack selection menu.

`banner` - The path to a custom banner that appears on the left side of the screen on the pack selection menu. It is recommended to set `showName` to `false` for this. Make sure it is in the same folder as the pack file.

![image](https://i.imgur.com/wmUWt4R.png)

If you've done it correctly, you should now see your custom pack in the menu.

![image](https://i.imgur.com/K7wX6gr.png)

# Mods

Mods are special effects you can enable in a modchart. You can adjust the intensity, speed, and easing of a mod.

Below are the mods that you can currently use as of Average4k b11.2.3.

## Non-Column-Specific Mods
These mods affect all columns in gameplay.

These mods are activated using `activateMod(modName, beat, beatLength, easing, amount)`

`modName` - The name of the mod.

`beat` - The time the mod begins in beats.

`beatLength` - The amount of time in beats it takes to tween to the `amount`.

`easing` - The ease function used to tween to the `amount`. For a list of easings, [use this link.](https://easings.net) Make sure this value is all lowercase.

`amount` - The amount the value tweens to. The way this works varies between mods, so be careful.

## Column-Specific Mods
These mods affect certain columns.

These mods are activated using `activateModMap(modName, beat, beatLength, easing, amount, col)`

`modName` - Same as above. Make sure the column-specific variant is being used here.

`beat` - Same as above.

`beatLength` - Same as above.

`easing` - Same as above.

`amount` - Same as above.

`col` - Which column you're applying the mod to. `0` is left, `1` is down, `2` is up, `3` is right.

All mods will display their column-specific variant next to the name `like this`. If there is no column specific variant, it is not available.

## Mod List

### drunk `drunkCol`
Affects the X-axis and waviness of the notes as they travel up.

[Click here to see the example video.](https://youtube.com/clip/UgkxmvWbWkBIFRbOgVq3JS0yC0U9sBreymjb)

### tipsy `tipsyCol`
Affects the Y-axis. Columns move up and down.

[Click here to see the example video.](https://youtube.com/clip/UgkxTOBNToeEdpwH3GML1eFJO9RmWvgTtk5O)

### aconfusion `confusion`
Receptors and notes rotate. Unlike other mods, the amount is the angle the notes rotate to.

[Click here to see the example video.](https://youtube.com/clip/Ugkx6A_sA1wB0HW0l4ZDi_jOUH5uzaTiUzlj)

### wave `waveCol`
Moves all notes in a wave-like action across the Y-axis. It is recommended that this should be used for slower scroll speeds.

[Click here to see the example video.](https://youtube.com/clip/UgkxIk70XgmSFHyk2el4kYF4YaT63CcR9YYc)

### dizzy
Rotates the notes depending on how far they are.

[Click here to see the example video.](https://youtube.com/clip/UgkxAViqxdQ7xzepPiqg0UIQEGiF5fTe66f9)

### amovex `movex`

Moves the playfield along the X-axis.

### amovey `movey`

Same as `amovex`, but it moves the playfield along the Y-axis.

### mini `miniCol`

Scales the playfield. Set to `0.5` by default. `1` is half the size and `0` is double of the current size.

### reverse

**This mod is only available on column-specific mods.**

Reverses the column's scrollspeed.

## Stealth
**This mod is only available on column-specific mods.**

Stealth is a mod that has multiple properties that can be adjusted. 

For an example of stealth, [click here.](https://youtube.com/clip/UgkxhvAM_LQBjpMaDgr4dsCj-gXXY75cU05D)

The following are:

### stealthOpacity

Sets a column's transparency.

### stealthWhite

Sets how white a column is.

### stealthReceptorOpacity

Same as `stealthOpacity`, but only affects the receptor of the column.

## Current Global Stuff
`config.downscroll` - The player setting for downscroll.

`config.noteSize` - The player setting for note scaling.

`setScrollSpeed(speed)` - Self explanatory.

`setNoteSkin(skin)` - Changes the noteskin. Noteskins added to modcharts must be added in the folder the modchart is in.

# Skinning

Skins visually change different aspects of the game, most notably the notes/receptors and the menu.

Below is a basic tutorial on how to create a skin in Average4k as of update b11.2.3.

## Getting Started
To create a skin, navigate to the Average4k folder from steam (Average4k->Settings->Manage->Browse local files), then go to `assets\noteskin`. In here is where all of the skins (including the default ones) are located.

From here, make a copy of one of the default skins, and rename it to whatever you like. You can now change all of the note images and edit the `config.skin` file, explained below.

## config.skin

This file holds some configuration options to change when creating your skin.

`rotate` (true/false) - Rotates the sprite's orientation depending on it's direction; Useful for arrow skins.

`shrink` (true/false) - Shrinks the receptors depending on if they are being held or not.

`bounce` (true/false) - Makes the combo and judgement text bounce when a note is played.

`disableQuant` (true/false) - Disables the note color quantization. If set to true, specify the image file to use for each lane. An example is shown below, where the directions specify the notes and the text following it specifies the image file name, without the extension.
```
left: image1
down: image2
up: image2
right: image1
```

### Skinning the menu

The final option in `config.skin` is `path`.

When set to `path: default` , the skin will take the default menu elements from the base game. In order to change the menu elements, follow the steps below:

1. In the `assets` folder, copy the entire `skinDefaults` folder.
2. Paste the folder in your custom skin folder, and rename it to whatever you want (I'll use `skinAssets` for the sake of this tutorial)
3. In `config.skin`, change the path to the name of the folder (`path: skinAssets`)
4. Skin the menu! All changes made to the images in this folder will apply to your game when your skin is selected.
