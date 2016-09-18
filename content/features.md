---
title: Features
weight: 20
---

The builder has the following features available when creating keyboard layouts.


## Plate Layout

The keyboard layout is specified by using the `Raw data` from the <a href="http://www.keyboard-layout-editor.com/" target="_blank">keyboard-layout-editor.com</a> (KLE) tool.  The data from KLE defines the layout of the keyboard, or the footprint of the keys.  

![layout][layout]

Once you have a layout specified, you can modify individual keys by adding or editing the key's details object.  This details object is a set of parameters defined inside curly brackets before the key. For example, *Tab* is defined as `{w:1.5},"Tab"`.

The following parameters can be specified to override the default settings on individual keys.

* **Rotate Switch Cutout `{_r:<degrees>}`:**  Example, `{_r:90},""`.  Rotate the switch cutout independent of the 
stabilizer cutout (assuming there is one).  
  Set in [Switch Type](#switch-type) / Adding `_r:90`  
  ![rotate_switch][rotate_switch]


* **Rotate Stabilizer Cutout `{_rs:<degrees>}`:**  Example, `{_rs:180},""`.  Rotate the stabilizer cutout independent of the switch cutout.  
  Set in [Stabilizer Type](#stabilizer-type) / Adding `_rs:180`  
  ![rotate_stab][rotate_stab]

* **Switch Cutout Type `{_t:<1-4>}`:**  Example, `{_t:1},""`.  Numbers are in the same order as the images.  
  Set in [Switch Type](#switch-type) / Adding `_t:1`  
  ![change_switch][change_switch]

* **Stabilizer Cutout Type `{_s:<0-4>}`:**  Example, `{_s:3},""`.  Numbers are in the same order as the dropdown list.  
  Set in [Stabilizer Type](#stabilizer-type) / Adding `_s:3`  
  ![change_stab][change_stab]

* **Cutting Kerf `{_k:<mm>}`:**  Example, `{_k:0.25},""`.  The kerf value for an individual switch/stabilizer cutout, 
this overrides the value set in the [Kerf](#kerf) section.  Values are in mm (without the unit).  
  Set in [Kerf](#kerf) / Adding `_k:1`  
  ![change_kerf][change_kerf]

Here is an example using all of them together: `{_r:90, _rs:180, _t:0, _s:2, _k:0.25},""`

[layout]: /images/features/layout.png "Keyboard Layout"
[rotate_switch]: /images/features/rotate_switch.png "Rotate Switch"
[rotate_stab]: /images/features/rotate_stab.png "Rotate Stabilizer"
[change_switch]: /images/features/change_switch.png "Change Switch Type"
[change_stab]: /images/features/change_stab.png "Change Stabilizer Type"
[change_kerf]: /images/features/change_kerf.png "Change Kerf"
<style>
	img[alt=rotate_switch],
	img[alt=rotate_stab],
	img[alt=change_switch],
	img[alt=change_stab],
	img[alt=change_kerf] {
		width: 250px;
	}
</style>


## Switch Type



## Stabilizer Type



## Case Type



## Hole Diameter
{{< note title="Note" >}}
Only applies to the `Poker` case type.
{{< /note >}}



## USB Cutout
{{< note title="Note" >}}
Only applies to the `Sandwich` case type.
{{< /note >}}



## Mount Holes
{{< note title="Note" >}}
Only applies to the `Sandwich` case type.
{{< /note >}}



## Edge Padding



## Plate Corners



## Kerf



## Line


