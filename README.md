# Video Synthesizer in Pygame

![Video Synthesizer Example](https://github.com/burningion/pygame-video-synthesizer/blob/master/images/preview.gif?raw=true)

This project uses Aubio and Onset Detection to create real time visual effects to accompany somebody playing music.

It accompanies a blog post and video available at [makeartwithpython.com](https://www.makeartwithpython.com/blog/video-synthesizer-in-python/).

## Usage

```bash
$ python3 video-synthesizer.py
```
You'll get back out a list of audio inputs built into your computer. You can then call the program again with the correct number for your chosen input, and play back in real time.

```bash
$ python3 video-synthesizer.py -input 3
```

You can then play away!

## Architecture

![Video Synthesizer Architecture](https://github.com/burningion/pygame-video-synthesizer/blob/master/images/guitar.png?raw=true)

We take in audio, in this example from a [Rocksmith](http://amzn.to/2A2HCjR) cable. We then pass the raw audio into a thread to handle and detect onsets within our Python program. 

This thread then pushes any detected onsets onto a queue, which is picked up by our main Pygame thread.

