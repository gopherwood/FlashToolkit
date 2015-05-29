# SpringRoll Flash Toolkit [![Build Status](https://travis-ci.org/SpringRoll/FlashToolkit.svg)](https://travis-ci.org/SpringRoll/FlashToolkit)

Adobe Flash Professional CC 2014 Commands for Exporting, Optimizing and Publish HTML5 Canvas document. While these commands are exclusive to using SpringRoll, there are a couple helper function for use with certain SpringRoll features.

## Installation

* Visit the latest release [here](https://github.com/SpringRoll/FlashToolkit/releases)
* Download **FlashToolkit.zxp** 
* Install ZXP with the [Adobe Extension Manager CC](https://www.adobe.com/exchange/em_download/).

## Usage

All the scripts are runable from the Commands menu within Flash Professional.

#### Exporting/Export BitmapMovieClip

Create JSON and spritesheet useable for `springroll.easeljs.BitmapMovieClip`. To use, select a MovieClip or MovieClips from the library to export then run the command.

#### Exporting/Export Frame Label Sequence

Export a sequence of PNGs based on the frame labels. Useful if you're creating spritesheets using TexturePacker. To use, run the command on the current timeline which contains frame labels.

#### Optimizing/Clear Extra Blank Keyframe

Remove all redundant clear keyframes, in order versions of CC 2014, blank keyframes added more filesize and produced playback issues in CreateJS. To use, run the command on the current timeline.

#### Optimizing/Filter Finder

Generate a report of all the MovieClips within the current project which contain filters (Color transforms, Drop shadows, etc). This is useful for tracking down and remove filters which harm performance. To use, simply run the command.

#### Optimizing/HTML5 Canvas Size Report

Generate a report of the output size of all the assets in an HTML5 Canvas published document. To use, publish the current document and then run the command.

#### Optimizing/Optimize Graphics

Remove all unused graphic frame from a selected graphic symbol in the library. To run, select a graphic from the library and then run the command.

#### Optimizing/Optimize Keyframe

Reduce the number of keyframes by eliminating keyframes that are similar. To run, navigate to a timeline of frames you would like to remove, then run the command. There are two values "Move Tolerance" and "Scale Tolerance". If two keyframes contain a symbol within those tolerance the second keyframe is removed. 

#### Timeline/Animation Event Label

Create animation event labels on the timeline which work with `springroll.easeljs.Animator`. To use, select a range of frames on the current timeline and run the command. This will prompt for an event name to create a start and end label for use with Animator. For instance, "idle" event name will create "idle" and "idle_stop" labels. Animator has two types of event labels, `stop` (stop at the end) and `loop` (return to the beginning and keep playing). 

#### HTML5 Canvas Post Publish

This is not a command. This script automatically is invoked whenever an HTML5 Canvas FLA is published. It does two things: first, a JSON file is created of the `lib.properties` (which contains the manifest, size, framerate, etc) of the current document. Also, the output file is optimize to better work with a JavaScript minification tool (e.g., [Uglify](https://github.com/mishoo/UglifyJS2)).

## License

Copyright (c) 2015 [CloudKid](https://github.com/cloudkidstudio)

Released under the MIT License.
