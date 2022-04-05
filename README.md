# Learning JUCE

JUCE is a big class with a lot of nested classes, methods and properties, a JUCE application is mostly going to be written in the JUCE class. New projects come with a JUCE app boilerplate.

## Basic

### Two main files (Plug-In)

[official docs](https://docs.juce.com/master/tutorial_code_basic_plugin.html)

- `source/PluginProcessor`: contains all the audio processing stuff
- `source/PluginEditor)`: contains the visual (GUI) part of the app

`PluginProcessor` and `PluginEditor` are like the backend and the frontend respectively.

### Two main audio processor methods

- `prepareToPlay`: initialization
- `processBlock`: a method that processes blocks of audio (received as an array).

`prepareToPlay` and `processBlock` are like `init` and `loop` on Arduino.

### Working with blocks of audio

Samples are processed in batches (called blocks) in the `processBlock` function, a block is an array of recent samples. A simple operation with the signal, like multiplying it with a number will have to be implemented as a loop that does the multiplication for each sample of the block.