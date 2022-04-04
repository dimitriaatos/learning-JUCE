# Learning JUCE

JUCE is a big class with a lot of nested classes, methods and properties, everything in a JUCE application is written in the the JUCE class. New projects have a number of methods already written.

## Basic

### Two main files

- `source/PluginProcessor`: contains all the audio processing stuff
- `source/PluginEditor)`: contains the visual (GUI) part of the app

`PluginProcessor` and `PluginEditor` are like the backend and the frontend respectively.

### Two main methods

- `prepareToPlay`: initialization
- `processBlock`: a function that processes blocks of audio (received as an array).

`prepareToPlay` and `processBlock` are like `init` and `loop` on Arduino.

### Working with blocks of audio

Samples are processed in batches (called blocks) in the `processBlock` function, a block is an array of recent samples. A simple operation with the signal, like multiplying it with a number will have to be implemented as a loop that does the multiplication for each sample of the block.