---
title: Pro Tips
weight: 30
---

The builder is a tool with a *LOT* of different options and possibilities.  As a result, there are quite a few different tips and tricks that can/should be documented.  If you know of additional tips which are not documented here, please [contribute](/contribute/) to the documentation.

## SVG to STL Conversion

If you want to 3D print a prototype of your design, you will need to convert the 2-dimensional SVG to a 3-dimensional STL file format in order for your 3D printer to be able to work with it.  I have created a video tutorial for how to do this conversion for your convenience.

{{< note title="Note" >}}
In the video I say to extrude the faces before you do the cut.  If you do this, it will take longer to do the cut.  After doing some testing I recommend that you do the cut of the unioned faces before doing the extrude in order to speed up the process.
{{< /note >}}

<div class="video-wrapper"><iframe width="560" height="315" src="https://www.youtube.com/embed/8CROo67W24M" frameborder="0" allowfullscreen></iframe></div>
<style type="text/css">
.video-wrapper {
	position: relative;
	padding-bottom: 56.25%; /* 16:9 */
	padding-top: 25px;
	height: 0;
}
.video-wrapper iframe {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
</style>



## Support Multiple Layouts

One of the most common questions I get is "How do I support multiple layouts?".  One of the most common examples is something like supporting both a stepped caps lock as well as a regular full touch caps lock in the same layout.  Another example is supporting both a regular right shift (2.75u) as well as a short right shift (1.75u + 1u) on the same layout.

``` json
["~\n`","!\n1","@\n2","#\n3","$\n4","%\n5","^\n6","&\n7","*\n8","(\n9",")\n0","_\n-","+\n=",{w:2},"Backspace"],
[{w:1.5},"Tab","Q","W","E","R","T","Y","U","I","O","P","{\n[","}\n]",{w:1.5},"|\n\\"],
[{w:1.25},"Stepped",{w:1.75,x:-1.25},"Caps Lock","A","S","D","F","G","H","J","K","L",":\n;","\"\n'",{w:2.25},"Enter"],
[{w:2.25},"Shift","Z","X","C","V","B","N","M","<\n,",">\n.","?\n/",{w:1.75},"ShortShift","Fn",{w:2.75,x:-2.75},"Shift"],
[{w:1.25},"Ctrl",{w:1.25},"Win",{w:1.25},"Alt",{a:7,w:6.25},"",{a:4,w:1.25},"Alt",{w:1.25},"Win",{w:1.25},"Menu",{w:1.25},"Ctrl"]
```

Note the following key definitions:
```
{w:1.25},"Stepped",{w:1.75,x:-1.25},"Caps Lock"
{w:1.75},"ShortShift","Fn",{w:2.75,x:-2.75},"Shift"
```

What we are doing here is actually placing two keys in the same space.  So we are defining one key, and then we are defining the next key and are using a negative `x` value to move it over top the previous key we defined.  The builder is smart enough to know what to do when you do this and it will union all the overlapping parts together to produce the required cutout to support the configuration.

Here is what this layout looks like when drawn with the default switch and stabilizer options:

![multi-layouts](/images/pro-tips/multi-layout.png "Multiple Layout Support")



## Save a DXF with Units

One of the most common issues people have when working with the files output from the tool is "Why is my drawing so big?".  Unfortunately, the DXF library I am working with is relatively old and does not support the `DXF 2007` file format which includes the Units of Measure.  My tool does everything in Millimeters, but it is not able to specify the units when the file is exported to a DXF.  Since the units are not defined in the file, your CAD program will assume the default units defined in your CAD program.  

To solve this problem, you need to open the file in a CAD program that can export the `DXF 2007` format, specify the units as Millimeters and then save as a `DXF 2007` file format.  <a href="http://librecad.org/cms/home.html" target="_blank">LibreCAD</a> is a free CAD software which I know supports the `DXF 2007` file format.

Here is the process in LibreCAD to re-save the exported DXF file to the `DXF 2007` file format.

* Download the DXF version of your CAD.
* Open it in LibreCAD
* Navigate to: **Edit** -> **Current Drawing Preferences** (`Command + ,` on a Mac)
* Select **Units** and change **Main drawing unit** to **Millimeter**
* Click **OK**
* Navigate to: **File** -> **Save as...**
* Save the file with type **Draw Exchange DXF 2007**

