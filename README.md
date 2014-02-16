# NOMAD

Original Documentation can be found [here](http://www.gerad.ca/nomad/Project/Home.htm).

## ABOUT

NOMAD - Nonsmooth Optimization by Mesh Adaptive Direct search - V. 3.6.1 -  2013/05

Copyright (C) 2001-2013

* Mark Abramson - *the Boeing Company, Seattle*
* Charles Audet - *Ecole Polytechnique, Montreal*
* Gilles Couture - *Ecole Polytechnique, Montreal*
* John Dennis - *Rice University, Houston*
* Sebastien Le Digabel - *Ecole Polytechnique, Montreal*
* Christophe Tribes - *Ecole Polytechnique, Montreal*

## CONTACT

Contact information:

  Ecole Polytechnique de Montreal - GERAD
  C.P. 6079, Succ. Centre-ville, Montreal (Quebec) H3C 3A7 Canada
  e-mail: nomad@gerad.ca
  phone : 1-514-340-6053 #6928
  fax   : 1-514-340-5665

## LICENCE

This program is free software: you can redistribute it and/or modify it under the
terms of the GNU Lesser General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.  See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along
with this program. If not, see <http://www.gnu.org/licenses/>.

## AUTHORS

* Mark A. Abramson (Mark.A.Abramson@boeing.com), The Boeing Company.

* Charles Audet (www.gerad.ca/Charles.Audet), GERAD and Departement de
mathematiques et de genie industriel, ecole Polytechnique de Montreal.

* J.E. Dennis Jr. (www.caam.rice.edu/~dennis), Computational and Applied
Mathematics Department, Rice University.

* Sebastien Le Digabel (www.gerad.ca/Sebastien.Le.Digabel), GERAD and Departement
de mathematiques et de genie industriel, ecole Polytechnique de Montreal.

* Christophe Tribes, GERAD, Departement de mathematiques et de genie industriel,
Department of mechanical engineering, ecole Polytechnique de Montreal.

## DESCRIPTION

NOMAD is a C++ implementation of the Mesh Adaptive Direct Search (MADS) algorithm,
designed for constrained optimization of black-box functions.

The project started in 2001, and was funded in part by AFOSR, CRIAQ, FQRNT, LANL,
NSERC, the Boeing Company, and ExxonMobil Upstream Research Company.

## WEB PAGE

http://www.gerad.ca/nomad/

## FURTHER INSTRUCTIONS :

Please visit the web page for futher instruction on the following:

* Downloading, configuring, compiling, and installing NOMAD
* Using NOMAD and setting the parameters
* Reports on NOMAD
* How to report bugs and make enhancement requests
* And more...

## BATCH OR LIBRARY MODE

NOMAD is designed to be used in two different modes : batch and library.
The batch mode is intended for a basic ans simple usage of the MADS method,
while the library mode allows more flexibility.

For example, in batch mode, users must define their separate black-box program,
that will be called with system calls by NOMAD.

In library mode, users can define their black-box function as C++ code
that will be directly called by NOMAD, without system calls and temporary files.

## TYPES OF USE :

There are two ways of using NOMAD, one can directly use an executable or compile
the source code.

NOMAD batch mode executable is located in directory $NOMAD_HOME/bin or %NOMAD_HOME%\bin.
In order to avoid compiling the code, you can simply use this executable.

## HOW TO EXECUTE NOMAD :

For informations about the execution of NOMAD, please read the user guide:

* $NOMAD_HOME/doc/user_guide.pdf
* http://www.gerad.ca/NOMAD/Downloads/user_guide.pdf

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/moxxxom/nomad/trend.png)](https://bitdeli.com/free "Bitdeli Badge")
