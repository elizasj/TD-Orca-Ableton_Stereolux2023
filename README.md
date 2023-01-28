# Workshop: Audio Reactive Visuals w/Touch Designer, Ableton & Orca

_This workshop explores the creation of generative and parametric visuals using TouchDesigner, and then integrating sounds with Ableton Live and Orca to produce realtime interaction between audio and visual components. The goal of this workshop is to provide you with a introductory overview of Touch Designer, as well as an understanding of how to use midi to power the animation of dynamic visuals being output by Touch Designer. You will leave with a simple set-up that can be used as a base/starting point (feel free to iterate and build out your own bespoke setup!) in the context of an artistic installation or an audiovisual performance._ <br />

## Contents

[Touch Designer](#td) <br />
[Orca](#orca) <br />
[Ableton](#ableton) <br />

## Touch Designer<a name="td"></a>

→ download [Touch Designer 2022.31030+](https://derivative.ca/download/archive)

### _Basics_

<details>
<summary>TOPS</summary>

_Deals with 2D space. Each pixel has an x,y position and an RGBA value associated with it, every TOP has a resolution_<br />

**RGBA**
![RGBA](/images/RGBA.png)

**Noise Patterns**
![Noise Patterns](/images/NoisePatterns.png)

**Wiggly Edges**
![Wiggly Edges](/images/WigglyEdges.png)

</details>

<details>
<summary>CHOPS</summary>

_Deals with 1d space, dealing with numerical data, channel based, and each channel is sample based. AKA they take in data. Chops drive other parameters in touch designer. Can be 1 chan/1 sample, or 1 chan/multiple samples…_

**Single channel, single sample**
![Single channel and sample](/images/singlesample.png)

**Single channel, single sample**
![Single channel many samples](/images/manysamples.png)

**Map initial range to new range**
![remap range](/images/remaprange.png)

**Pattern OP as driver of other params**
![pattern op](/images/patternop.png)

**Lag OP to smooth out dynamic data**
![lag op](/images/lagop.png)

**Filter OP to smooth out dynamic data (similar to Lag, nuanced difference)**
![filter op](/images/filterop.png)

</details>

<details>
<summary>SOPS</summary>

_Deals with 3d space. SOPs can generate, import, modify and combine 3D surfaces (aka geometries)_

**3D object basics**
![baics](/images/3dbasics.png)

**Combining 3d objects into same 3d space**
![combine](/images/3dcombine.png)

**Animating 3d objects in same 3d space**
![animate](/images/3danimate.png)

**Deform 3d shapes (noise)**
![noise](/images/3dnoise.png)

**Deform 3d shapes (twist)**
![twist](/images/3dtwist.png)

**Order of Operations**
![order](/images/ooo.png)

**3D Rendered scene**
![lag op](/images/3drender.png)

</details>

<details>
<summary>MATS</summary>

_MATs used to create materials for geometry. They apply shaders to SOPs or 3D Geometry Objects for rendering textured surfaces with lighting._

**3D Rendered scene**
![materials](/images/materials.png)

</details>

<details>
<summary>COMPS</summary>

_These elements help in composing the different creative sketches you are interested in making._

_COMPs are unique compared to other operator families in that they contain their own networks. They contain everything from geos, to basic lights, to ui elements like buttons, sliders, and directories (Base, Container… etc)_

**Setting default values**
![defaults](/images/defaults.png)
![defaults2](/images/defaults2.png)

</details>

### _Advanced Topics_

<details>
<summary>Audio</summary>

_TD is not really a programm for audio production, but it’s great for analysis. It’s very common to see a DAW like Ableton paired with TouchDesigner for live shows. Types of data that can be handled include MIDI and OSC. Audio can be routed in and out of both. Here, the mic and an mp3 will be used._

**audio/mic & noise**
![audio mic](/images/audio_mic.png)

**audio as time**
![audio as time](/images/audio_time.png)

</details>

<details>
<summary>Feedback</summary>

_The Feedback TOP can be used to create feedback effects in TOPs. It can give fake motion blur by not clearing the color buffer. A buffer is simply a chunk of memory used to hold data. Color buffers contain color-index or RGB color data and may also contain alpha values._

**Basic Feedback Loops**
![feedback loops](/images/feedback.png)

</details>

<details>
<summary>Instancing</summary>

_Geometry instances in the are copies of the geometry object, which can be transformed independently. An instance doesn't actually have its own data, but rather just refers to an OP (or has an input) whose data it uses._

**Instancing**
![instancing](/images/instancing.png)

</details>

<details>
<summary>TD Ableton</summary>

_TD Ableton is a really handy package for bridgin Ableton with Touch Designer. It gives aggess to tracks, audio and midi notes & velocities_

**TD Ableton**
![tdableton](/images/tdableton.png)

</details>

## Orca<a name="orca"></a>

→ download [Orca](https://hundredrabbits.itch.io/orca) <br />
→ download [LoopMidi](http://www.tobias-erichsen.de/software/loopmidi.html) (PC) / [IAC Bus](https://help.ableton.com/hc/en-us/articles/209774225-How-to-setup-a-virtual-MIDI-bus) (Mac)

Orca is a language comprised of [26 functions](https://github.com/hundredrabbits/Orca), one for every letter of the alphabet. It's also a live coding environment, inside which you can use your arrow keys to move around.

- Arrows + `ctrl` to jump across cells
- `Shift` + `arrows` to select blocks
- Drag blocks of highlighted code around by holding down `alt`
- `Ctrl` + `i` for insert mode to type normally

Add a `D` (_Delay_) to your environment and you'll see a flashing star, `*`, appearing at regular intervals right underneath the letter. This is called a **bang**, and is a core concept in Orca - everything you do in Orca is at the service of creating bangs. Which represent the sequences and patterns we'll be making as they are sent out from Orca toward other software set up to receive them (Live or Unity for example.)

The `D` we just set up will flash a bang every 8 frames unless changed through *mod*, the optional property to the right of the `D`. Notice there is also a parameter to the left. If you place the cursor on top of this parameter, you'll see a hint about what it does appear at the bottom left corner of your Orca window. Play with adding numbers to either side of `D` to understand how to speed up and slow down your bang.

In order to interface with other software, we'll need to assign a data format to our bangs. As mentioned, we'll be working with MIDI, which Orca sends using the colon symbol `:` It comes with five parameters - channel, octave, note, velocity & length. You'll need the first three parameters to make any kind of sound or visual, the last two can be left empty.

<details>
<summary>An example of this would be:</summary>

![orca](/images/image.gif)

</details>

A brief overview of the MIDI parameters: **octave** and **note** refer to the pitch of a sound, while **velocity** has to do with the loudness/quietness of said pitch. **Length** is how long the pitch holds before petering out. You can play with these four elements to make some pretty interesting sound and visual variations.

⚠️ The first parameter, **channel**, represents the address we're sending our bang to be interpreted in other software, which in our case is Live and Unity.

Now that you know how to create and send a bang, I suggest playing around with how you might combine any of the following:

- `R` *Random*, generates a random value
- `C` *Count*, same idea as D but only counts, no bang
- `B`_Bounce_, outputs the difference between two numbers
- `T` *Track*, creates sequences of notes to iterate through
- `V` *Variable*, stores values and use elsewhere on the grid
- `K` *Konkat*, outputs a bunch of variables at once

At any point, hit CMD + G and Orca's documentation will appear in the window. Yes, the docs are sparse. All the more reason to experiment, play and see what happens!

Remember to place your cursor over the white and green dots that appear around the letters to see what the parameters are for.

## Ableton<a name="ableton"></a>

→ download [Ableton](https://www.ableton.com/en/trial/)

> If you're on a PC, make sure you've got LoopMidi already running for this next part.

With Live open in Session View, where all tracks are organised into columns, you can begin setting up the audio samples and effects you want to use. Each column also has a bottom zone with the header Midi From. This is where you set your driver. On a Mac you'll set IAC Bus, on a PC you'll set LoopMidi. Then you choose the channel you want to receive on this track, incoming from Orca.

![loopmidi](/images/loopmidi.png)

⚠️ Where Live counts up from Channel 1, Orca counts up from Channel 0. So keep that in mind when you're jumping between software. Live Channel 1 == Orca Channel 0 ...etc.

Now it's time to get curious and creative with sound. Live has a lot to offer in terms of instruments and effects, if you don't yet have your own to play with. Live's integrated samples can be drag-&-dropped onto any MIDI column. For audio samples, you'll need to first create a Simpler instrument, then drag and drop audio effects on top of the instrument, (not the column, but the instrument just below where it says Drop Sample Here.) To add Midi or Audio Effects do the same:

<details>
<summary>adding a midi sample</summary>

![loopmidi](/images/midisample.gif)

</details>

<details>
<summary>adding an audio sample with Simpler sampler</summary>

![loopmidi](/images/simplersampling.gif)

</details>

<details>
<summary>adding MIDI and audio effects to samples</summary>

![loopmidi](/images/addingfx.gif)

</details>
