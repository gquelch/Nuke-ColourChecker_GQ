# ColourCheckerTool
## Documentation

I designed this tool to be able to better make use of Macbeth charts for VFX projects.

The idea was having a more streamlined way of compare your Render and Reference colour checkers, being able to view either one on top of the other, so you can closely match up the colours

Correct digital MacBeth charts can be found [here](http://www.nukepedia.com/gizmos/draw/x-rite-colorchecker-classic-2005-gretagmacbeth) in many colourspaces, as EXR download or Nuke Gzimo.

<br></br>

### Workflow

There are a lot of automated tools out there for using a Macbeth chart in Nuke, such as [mmColorTarget](http://www.nukepedia.com/gizmos/colour/mmcolortarget), but often you want to have manual control over the result, for instance mmColourTarget will output a colour matrix, which isn't simple to tweak if you want to use this to grade your CG element. 

With this workflow you can simply copy the grade nodes over to your CG elements and use them as a starting point for the comp.

First step is to set position of Reference colour checker. You want to position all 4 points on the corners of your checker

![ColourCheckerTool%20663d958d40ee4b2fb4546f4235bcab0d/Untitled.png](ColourCheckerTool%20663d958d40ee4b2fb4546f4235bcab0d/Untitled.png)

Then you want to do the same process for your Render checker

![ColourCheckerTool%20663d958d40ee4b2fb4546f4235bcab0d/Untitled%201.png](ColourCheckerTool%20663d958d40ee4b2fb4546f4235bcab0d/Untitled%201.png)

You now have 3 options for displaying your colour checkers

- Merged

    This places your Render checker on top of the Reference checker in the plate, good for checking the colours in situ

    "Disable Masking" will switch this display to view the full Render checker, without masking, on top of the plate

- Ref / Render

    This will be a full screen display of your Reference, on top of your Render. Viewing the Alpha channel of this output will display the Saturation values of your checkers.

- Render / Ref

    This will be a full screen display of your Render on top of your Reference. Viewing the Alpha channel of this output will display the Saturation values of your checkers.

You can now start using colour nodes to adjust the value and saturation of your render checker in order to match it to your reference, check the saturation by viewing the Alpha channel.

I work through channel by channel (R G B A(saturation when using this node) Y) and make small adjustments to start aligning the colours.

You can spend as much time as you like tweaking the values to get a match for your plate, I often get something that is quite close, but knowing they will only be a base and I will be tweaking them artistically later, I don't spend hours on it.

Here is a rough match up for my checkers, viewed with *Render / Ref*, you would spend more time doing this with a real Render, I have just done this quickly for demonstration purposes

![ColourCheckerTool%20663d958d40ee4b2fb4546f4235bcab0d/Untitled%202.png](ColourCheckerTool%20663d958d40ee4b2fb4546f4235bcab0d/Untitled%202.png)

I can now take these grade nodes and copy them to my CG render, and in theory, we have a starting point for our comp with nicely matched colours to our plate. In an ideal workflow, with a good HDR and reference colour checker, you shouldn't need to do much grading for it to match, the closer the initial render, the better job you have done recreating the real world lighting.