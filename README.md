# Virtual Retina - Download

| ![retina logo](index_files/retinalogo_small) |
|-----------------------------------------------|

**Virtual Retina**
*Large scale simulator of biological retina*
INRIA CeCILL C open-source license (2007)
Partially supported by the [EC IP project FP6-015879 FACETS](http://facets.kip.uni-heidelberg.de/)
**[Odyssée research-team](http://www-sop.inria.fr/odyssee/), [INRIA Sophia Antipolis - Méditerranée](http://www-sop.inria.fr/)**

---

| [Overview](http://www-sop.inria.fr/odyssee/software/virtualretina/index.shtml) | [Web-service](http://facets.inria.fr/retina/webservice.html) | [Results](http://www-sop.inria.fr/odyssee/software/virtualretina/results.shtml) | [Customization](http://www-sop.inria.fr/odyssee/software/virtualretina/customization.shtml) | [Download](http://www-sop.inria.fr/odyssee/software/virtualretina/download.shtml) | [Publications](http://www-sop.inria.fr/odyssee/software/virtualretina/publications.shtml) | [Contact](mailto:adrien.wohrer@inria.fr,pierre.kornprobst@inria.fr) |

---

## Technical prerequisites

- Runs under Linux. Compiled with gcc version 3.4 or more.
- Also runs under [mac](http://www-sop.inria.fr/odyssee/software/virtualretina/other_files/mac.pdf) (thanks to [Horacio.Rostro_Gonzalez@sophia.inria.fr](mailto:Horacio.Rostro_Gonzalez@sophia.inria.fr)).
- Required helper softwares (included in the archive):
  - **MVASpike**, an event-driven neural network simulation software
  - **CImg**, an image processing library
  - **libxml++**, an xml parsing software
  - **xmlParameters++**, a small helper library producing an interface between c++ parameters and an xml tree.

## Download

[retina_package.tar.gz](http://www-sop.inria.fr/odyssee/software/virtualretina/other_files/retina_package.tar.gz) is the archive with *Virtual Retina* and other required libraries. It also contains the tutorial explaining in detail both installation and usage of the software.

## Installation

A shell command performs an automatic installation of all libraries. Basic directions are also provided in the tutorial (included in the archive; also available [here](http://www-sop.inria.fr/odyssee/software/virtualretina/other_files/tutorial.pdf)) for those wishing to perform a custom, manual installation.

## Tutorial

A [tutorial](http://www-sop.inria.fr/odyssee/software/virtualretina/other_files/tutorial.pdf) is available, explaining both installation procedure and usage of the software in detail. Some README files in the archive also contain some information. Typically, the program is called under a LINUX shell, with a syntax that looks like this:

| Retina&nbsp;&nbsp; path/to/my/test_sequence*.pgm &nbsp; -ret my_retina.xml&nbsp; -r 10&nbsp; -outD path/to/my/saving/directory |
|-------------------------------------------------------------------------------------------------------------|

with possible options:

- **test sequences** can be 2d frames under any usual format (as here), or directly a .inr 3-dimensional file.
- **-ret** gives the path to the [retina definition file](http://www-sop.inria.fr/odyssee/software/virtualretina/index.html#customization) in xml format.
- **-r** 10: each input frame is presented to the retina for a duration of 10*(retinal time step) = 50 ms in this case.
- **-outD**: path to the directory where all simulation files will be saved.
- etc. Full list of options by typing **-h**.

*Virtual Retina* contains a number of customized retina definition files that you can directly use to start your first simulations.

## Log file

A [log file](http://www-sop.inria.fr/odyssee/software/virtualretina/other_files/VIRTUAL_RETINA_LOG_FILE.txt) has been created to keep track of the successive changes in the format required for the XML definition file.

## Retina schema

If you want to create a Retina configuration file, you can find a RelaxNG schema of the options you must provide there: [retinaSchema.rng](http://www-sop.inria.fr/odyssee/software/virtualretina/retinaSchema.rng).
So you should be able to validate your Retina configuration file with a command like that (`xmllint` is part of libxml package):
`xmllint your_xml_file.xml --noout --relaxng retinaSchema.rng`

<br>

---

2025-06-02: Converted README to Markdown.