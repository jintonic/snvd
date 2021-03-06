# neus - neutrinos from supernovae

It is a C++ library providing neutrino energy, number luminosity spectra and their time evolutions.
Two supernova models are included, 
the [Nakazato model](http://asphwww.ph.noda.tus.ac.jp/snn/) and 
the [Livermore model](http://stacks.iop.org/0004-637X/496/i=1/a=216).

##### Compilation and Installation
Since the database of Nakazato model is loaded to the
[TH2D](http://root.cern.ch/root/html/TH2D.html) and 
[TH1D](http://root.cern.ch/root/html/TH1D.html) objects provided by
[ROOT](http://root.cern.ch),
the library has to be compiled against [ROOT](http://root.cern.ch) libraries.
The database files have to be downloaded from http://asphwww.ph.noda.tus.ac.jp/snn/
and extracted to the local machine.

The intepolation of Livermore model is provided in 
https://github.com/jintonic/total,
the library has to be compiled against it as well.
The location of the locally installed
https://github.com/jintonic/total library
can be specified in the second line of the [makefile](Makefile).

```make && make install``` will compile the library libNEUS.so and
copy it to ```/prefix/lib/```. 
The header files will be copied to ```/prefix/include/NEUS/```.
The prefix can be specified in the first line of the [makefile](Makefile).

##### Usage
The usage of classes is demonstrated in *.C files. 
The following code snippets have to be included in the main program to use the library.
```cpp
#include <NEUS/NakazatoModel.h>
using namespace NEUS;
```

All output values are divided by 1e50 to move them to a range that TH2 can handle.
