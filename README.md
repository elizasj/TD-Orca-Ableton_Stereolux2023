# Workshop: Audio Reactive Visuals w/Touch Designer, Ableton & Orca

_This workshop explores the creation of generative and parametric visuals using TouchDesigner, and then integrating sounds with Ableton Live and Orca to produce realtime interaction between audio and visual components. The goal of this workshop is to provide you with a introductory overview of Touch Designer, as well as an understanding of how to use midi to power the animation of dynamic visuals being output by Touch Designer. You will leave with a simple set-up that can be used as a base/starting point (feel free to iterate and build out your own bespoke setup!) in the context of an artistic installation or an audiovisual performance._ <br />

## Touch Designer

###### TOPS

_2D space. Each pixel has an x,y position and an RGBA value associated with it, every TOP has a resolution_<br />

**RGBA**
![RGBA](/images/RGBA.png)

**Noise Patterns**
![Noise Patterns](/images/NoisePatterns.png)

**Wiggly Edges**
![Wiggly Edges](/images/WigglyEdges.png)

###### CHOPS

_1d space, dealing with numerical data, channel based, and each channel is sample based. AKA they take in data. Chops drive other parameters in touch designer. Can be 1 chan/1 sample, or 1 chan/multiple samples…_

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

###### SOPS

_3d space. SOPs can generate, import, modify and combine 3D surfaces (aka geometries)_

**3D object basics**
![lag op](/images/3dbasics.png)

**Combining 3d objects into same 3d space**
![lag op](/images/3dcombine.png)

**Animating 3d objects in same 3d space**
![lag op](/images/3danimate.png)

**Deform 3d shapes (noise)**
![lag op](/images/3dnoise.png)

**Deform 3d shapes (twist)**
![lag op](/images/3dtwist.png)

**Order of Operations**
![lag op](/images/ooo.png)

**3D Rendered scene**
![lag op](/images/3drender.png)
