# pyDCONTINPALS
Copyright (c) 2020 Danny Petschke (danny.petschke@uni-wuerzburg.de). All rights reserved.<br><br>

pyDCONTINPALS - A PYTHON program for running the historical FORTRAN code CONTIN-PALS initially provided by Provencher (1982) [1] and Gregory et al. (1990) [2,3]. CONTIN-PALS program solves Fredholm integral equations with convoluted exponential decays as kernels of the type that occur in the analysis of Positron Annihilation Lifetime Spectra (PALS).<br><br>

![demo](/demo.png)

# Quickstart Guide

pyDCONTINPALS consists of 3 files ...

- pyDCONTINPALS.py
- pyDCONTINPALSInput.py
- pyDCONTINPALSSpecSimulator.py

1. edit (or leave it as it is) <b>pyDCONTINPALSInput.py </b>:

```python
__demoMode                  = True # disable if running from real data

# NOTE: spectrum and IRF (or mono-exponential decay spectrum) data vectors require equal length!

# file path (and name) to the SPECTRUM data:
__filePathSpec              = 'testData/spectrum_10ps.dat'
__specDataDelimiter         = '\t'

# file path (and name) to the IRF data:
__filePathRefOrIRFSpec      = 'testData/ref_10ps.dat'
__refDataDelimiter          = '\t'

# define the number of rows, which should be skipped during the import (e.g. for ignoring the header entries):
__skipRows                  = 5;

# fixed mono-decay component in units of picoseconds [ps] (1/lambda = tau):
# Note: set to something like 1E-6 if you provide numerical IRF data as input
__tau_monoDecaySpec_in_ps   = 182.0  #[ps]

# grid of characteristic lifetimes with equally distributed grid points defining the resulting intensity spectrum
__gridTau_start             = 50.0   # [ps]
__gridTau_stop              = 3000.0 # [ps]
__gridPoints                = 100    # 10 ... 100 Note: this value is internally limited to 100 by CONTIN

# channel/bin resolution [ps]
__channelResolutionInPs     = 50.0  # >= 10 ... Note: this value is internally limited by CONTIN

# background estimation:
__bkgrd_startIndex          = 800;
__bkgrd_count               = 190; # number of channels with respect to the 'startIndex'
```
2. execute <b>pyDCONTINPALS.py</b><br>

3. finished. You should see the results as shown above in the figure if you are running in the demo mode <i>(__demoMode = True)</i>.

# How to cite this Program?

Before citing this program <b>pyDCONTINPALS</b> you need at least to cite the initial publication of the FORTRAN program <b>CONTIN-PALS</b> provided by Gregory et al. [2].

[R.B. Gregory, Y. Zhu, Analysis of positron annihilation lifetime data by numerical laplace inversion with the program CONTIN, Nucl. Instruments Methods Phys. Res. Sect. A Accel. Spectrometers, Detect. Assoc. Equip. 290 (1990) 172–182. doi:10.1016/0168-9002(90)90358-D.](https://doi.org/10.1016/0168-9002(90)90358-D).

You can cite all versions of pyDCONTINPALS by using the <b>DOI 10.5281/zenodo.1255105</b>. This DOI represents all versions, and will always resolve to the latest one.<br>

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1255105.svg)](https://doi.org/10.5281/zenodo.1255105)

## v1.x
pyDCONTINPALS v1.0:<br>[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1255106.svg)](https://doi.org/10.5281/zenodo.1255106)<br>

# Requirements
- [NumPy](http://www.numpy.org/) 
- [matplotlib](https://matplotlib.org/)<br>

#### [WinPython x64](https://sourceforge.net/projects/winpython/) meets all requirements. 

# License of pyDCONTINPALS (BSD-3-Clause)

Copyright (c) 2020 Danny Petschke (danny.petschke@uni-wuerzburg.de). All rights reserved.<br><br>

Redistribution and use in source and binary forms, with or without modification,<br> 
are permitted provided that the following conditions are met:<br><br>

 1. Redistributions of source code must retain the above copyright notice<br>
    this list of conditions and the following disclaimer.<br><br>

 2. Redistributions in binary form must reproduce the above copyright notice,<br> 
    this list of conditions and the following disclaimer in the documentation<br> 
    and/or other materials provided with the distribution.<br><br>

 3. Neither the name of the copyright holder "Danny Petschke" nor the names of<br> 
    its contributors may be used to endorse or promote products derived from <br>
    this software without specific prior written permission.<br><br>


 THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS<br> 
 OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF<br> 
 MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE<br> 
 COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,<br> 
 EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF<br> 
 SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION)<br> 
 HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR<br> 
 TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE,<br> 
 EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.<br>
 
 see also [BSD-3-Clause License](https://opensource.org/licenses/BSD-3-Clause)
 
 # License of DCONTINPALS (GNU General Public License) 
 Copyright (c) 2020 Danny Petschke (danny.petschke@uni-wuerzburg.de) All rights reserved.<br><br>

<p align="justify">This program is free software: you can redistribute it and/or modify<br>
it under the terms of the GNU General Public License as published by<br>
the Free Software Foundation, either version 3 of the License, or<br>
(at your option) any later version.<br><br>

This program is distributed in the hope that it will be useful,<br>
but WITHOUT ANY WARRANTY; without even the implied warranty of<br>
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.<br><br></p>

For more details see [GNU General Public License v3](https://www.gnu.org/licenses/gpl-3.0)

# References 
[1] [S.W. Provencher, CONTIN: A general purpose constrained regularization program for inverting noisy linear algebraic and integral equations, Comput. Phys. Commun. 27 (1982) 229–242. doi:10.1016/0010-4655(82)90174-6.](https://doi.org/10.1016/0010-4655(82)90174-6)<br>

[2] [R.B. Gregory, Y. Zhu, Analysis of positron annihilation lifetime data by numerical laplace inversion with the program CONTIN, Nucl. Instruments Methods Phys. Res. Sect. A Accel. Spectrometers, Detect. Assoc. Equip. 290 (1990) 172–182. doi:10.1016/0168-9002(90)90358-D.](https://doi.org/10.1016/0168-9002(90)90358-D).<br>

[3] [R.B. Gregory, Analysis of positron annihilation lifetime data by numerical Laplace inversion: Corrections for source terms and zero-time shift errors, Nucl. Inst. Methods Phys. Res. A. 302 (1991) 496–507. doi:10.1016/0168-9002(91)90367-Y.](https://doi.org/10.1016/0168-9002(91)90367-Y)
