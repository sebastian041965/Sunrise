#Sunrise Project
##Introduction

The Sunrise Project is a research project, that aims to design an Open Source  hackable DLP based 3D printing system.

##Approach
The intention is to make the machine accesible to the general public. It must be sourceable, craftable, and modifiable by everyone. It aspires to be a platform for the community to explore this technology. Mechanics are scalable, source is available and modifiable, tools are open and obtainable.

##The technology

DLP 3D Printing uses photopolymierizing resin to craft the parts. Parts generate layer by layer as they are cured by a projector that outputs the cross-sections of the part, into the resin. There are various mechanical structures that can be used to achieve this.

This machine has what is called a _Bottom-Up_ structure. It has a vat, with transparent bottom, filled with resin. Underneath, an upward pointing DLP projector shoots light through the bottom window. The light striking on a **downward pointing** build surface cures the resin, forming a new layer.
Repeating this process, curing one layer below the previous one, ends up crafting the whole part, **upside down**.


<img src="./doc/2015-04-13-Prototipo-1-diagrama-bloques/Diagrama-bloques.png" width="300" align="center">

##The machine


<img src="./doc/README/Sunrise02.png" width="200" align="center">


This machine tries to stick to the RepRap philosophy, so structure and moving parts are 3D printed. Motion control is performed by an Arduino with a CNCShield, running a version of [GRBL][GRBL-link] that can be found [here][Sunrise-fw].
The projector is an [Optoma ML750][Optoma-link], with hacked optics for nearer focus.
PDMS based vat and flexible bottom vat system are being considered.


##About this repo

This repo contains the mechanical structure source. The tool of use is FreeCAD.
Folder content is descripted below
* `src`: Source files and assembly.
* `Step`: Step files for CAD import.
* `stl`: stl files for 3D printing.
* `FEM`: Part file duplicates for possible FEM analysis.
* `Fonts`: Fonts used in the design of the parts.
* `doc`: useful files for documentation
* `Software`: Provisional, holds useful software until it gets big enough for it to have its own repo.

###Cloning this machine

To build this machine, you need to print the 3D printable parts in [the stl folder][stlfolder]. You need to print each file once.
You can also find plates for 20x20cm bases and Witbox bases in [this folder][plates], so you can clone the machine in less prints.

You will also need:
* 1958 mm of 20x20 aluminium extrusion profile
* 1378 mm of 30x30 aluminium extrusion profile
* Smooth rods, depending on desired Zaxis length
* Hammerhead nuts (Around 196 for 20x20 profiles and 52 for 30x30)
* DIN912 M4x8 bolts for 20x20 hammerhead nuts
* DIN912 M6x10 bolts for 30x30 hammerhead nuts
* 2 M3x10 Bolts
* 1 M3x20 Bolt
* 1 M3x30 Bolt
* A hacked Optoma ML750 (Focus moved forward with a M2 nut)

The length of the pieces of aluminium profiles and smooth rods can be seen in the [assembly file][Assembly]. Due to this being still in development there's not a lot of documentation. If you have any doubts feel free to ask.

###Contributing to this repo

You can contribute to this repo by forking it, and making pull requests to the Development branch. If you find problems to make the contribution this way, [place an issue][issue] and we'll work it out.

Due to FCStd files being unmergeable, SunriseAssembly.FCStd is modified only on the Development branch. It may not be included in pull requests.

In case of contributing using gitflow, and to take advantage of git diff features on FCStd files, and avoid big commit files, paste this lines on .git/config:
```
[include]
    path = ../.gitconfig
```
These will include the particular repo configuration, that tells git to unzip the files before diffing them.


##History

###Sunrise v0.3 (In development)

####Target Specs

#####Primary
* Easier assembly and printing.
* Use just one size of profiles.
* Improve ZAxis performance by adding weight to the carriage.

#####Secondary
* Build environment enclosure.
 * Must be compatible with fast vat swapping. (Vat may go out by pulling from it, rather than lifting it)
 * Zcarriage will access the environment through a bellow
 * Will have a door
* Bellow for projector. UV light must not get out of the bellow.

###Sunrise v0.2

<img src="./doc/README/Sunrise02.png" height="285" align="center"><img src="./doc/README/Sunrise02real.jpg" height="285" align="center"><img src="./doc/README/Sun02Sappho.jpg" height="285" align="center">

####Specs:
* Motor assisted projector axis for resolution adjustment.
* Aluminium extrusion profiles + printed parts based structure. Way more rigid than v0.1.
* Hacked [Optoma ML750][Optoma-link] pico-projector.
* Expandable design, able to hold several projectors.
* [Arduino UNO][AU-link] + [CNCShield][CNCS-link] + [a modified GRBL][Sunrise-fw] for motion control.
* [Creation Workshop][CW] as slicer and projector control.
* QuickFit for easy replacement of the vat.


###[Sunrise v0.1][Sunrise-v0.1]

<img src="./doc/README/Sunrise01.png" width="200" align="center"><img src="./doc/README/Sunrise01real.JPG" height="273" align="center"><img src="./doc/README/Sun01Sappho.JPG" height="273" align="center">

####Specs:
* Threaded rod + printed parts based structure.
* Hacked [Optoma ML750][Optoma-link] pico-projector used to save space.
* Modular setting for easy technique testing.
* [Arduino MEGA][AM-link] + [RAMPS][RAMPS-link] + [Marlin][Marlink] for motion control.
* [Creation Workshop][CW] as slicer and projector control.
* PDMS coated resin vat.

##Credits
To everyone with the courage to go open source and contribute to humankind's DLP 3D printing knowledge

* To Clone Wars Barcelona for [ResinCAT3D][Resincat]
* To the Eraikizpi team for [Eraikizpi][Erai]
* To the PrintThatS**t team for [ResinCATPTS][PTS]
* To [BuildYourOwnSLA][BYOSLA] forum
* Michael Joyce from B9Creations for [B9Creator][b9c]
* To EnvisionLabs, for [Creation Workshop][CW]

Thank you 


##License


<img src="./doc/LICENSE/by-sa.png" width="200" align = "center">

This machine is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/). Please read the LICENSE files for more details.

Esta maquina tiene una licencia [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/). Por favor, lea los ficheros LICENSE para más detalles


[GRBL-link]: https://github.com/grbl/grbl
[Sunrise-fw]: https://github.com/bq/Sunrise-fw
[Sunrise-v0.1]: https://github.com/bq/Sunrise/releases/tag/0.1
[CW]: http://www.envisionlabs.net/
[Marlink]: http://reprap.org/wiki/Marlin
[RAMPS-link]: http://reprap.org/wiki/RAMPS_1.4
[AM-link]: https://www.arduino.cc/en/Main/arduinoBoardMega
[AU-link]: https://www.arduino.cc/en/Main/arduinoBoardUno
[CNCS-link]: http://blog.protoneer.co.nz/arduino-cnc-shield/
[Optoma-link]: http://www.optomausa.com/projectordetails.aspx?PTypeDB=Business&PC=ML750
[BYOSLA]: http://www.buildyourownsla.com
[Erai]: http://reprap.org/wiki/Eraikizpi
[Resincat]: http://reprap.org/wiki/ResinCat_3D/es
[PTS]: http://reprap.org/wiki/ResinCat_3D_PTS
[b9c]: http://www.b9c.com/
[plates]: ./stl/plates
[Assembly]: ./src/SunriseAssembly.FCStd
[stlfolder]: ./stl
[issue]: https://github.com/bqlabs/Sunrise/issues/new