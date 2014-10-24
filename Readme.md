#How-to install SimpleScalar on Ubuntu#
[SimpleScalar](http://www.simplescalar.com/) is a VLIW processor simulator. It permits to access measures like execution time, caches misses, and branch mis-prediction rate. It is entirely scalable: cache size and type, number of UAL entities, branch predictor type are customizable. It may be used as a tool for understanding Design-Space-Exploration. Unfortunately, the installation is quite complex due to an outdated code source.

The following script intends to automate the installation process with Ubuntu. It has been tested with Ubuntu 12.04 and gcc 4.6. It may not resolve all the errors you will have to face: don't hesitate to contact me (see my resume) if you think the script has to be improved. If you can choose not to use this simulator, you may want to have a glance at other simulators like [SoCLib](http://www.soclib.fr/) or [gem5](http://www.m5sim.org/). A more exhaustive list is available at [wikipedia (en)](http://en.wikipedia.org/wiki/Computer_architecture_simulator#Implementations)
## The script ##
Install-SimpleScalar.sh will create ~/SimpleScalar, and install SimpleScalar in it.
Set the script as executable (chmod +x Install-SimpleScalar.sh), run it, this it it! You may be able to compile your first program using a command-line such as: "`sslittle-na-sstrix-gcc -x c++ main.c`"
## Miscellaneous ##

- gcc 2.6 does not accept inline comments with C. A simple workaround is to compile your C-code as if it was a C++ code: use for instance `sslittle-na-sstrix-gcc -x c++ main.c`
- You may want to change some compilation flags in the SimpleScalar MakeFile: Replace "`-O0`" by "`-O3 -march=native -fstrict-aliasing`" and removing the "`-DDEBUG`" flag gives a substantial speed gain (near x2.0)
- Dimensioning your architecture is based on a compromise: Cache speed decrease with size. For a quantitative idea of the speed you can expect from a [cache](http://en.wikipedia.org/wiki/Cache_%28computing%29), you may be interested by the tool [CACTI](http://www.hpl.hp.com/research/cacti/), luckily far more simple to install than SimpleScalar.

## Connected links ##

Are you stuck with a bug not described here? You may find the solution in the following guides:

- [Simple Scalar Installation Tips](http://www.cse.iitd.ernet.in/~drajeswari/ss_installn.html)
- [Install SimpleScalar on Ubuntu 10.10 with Gcc-4.4](http://zealoct.wordpress.com/2011/04/19/install-simplescalar-on-ubuntu-10-10-with-gcc-4-4/)
- [McAiT (Rev 1.0) User Manual](http://www.neu-rtes.org/mcait/McAiT_UM_1.0.pdf)
- [Installing SimpleScalar: common problems and their solutions](http://www.neu-rtes.org/mcait/simplescalar_install_notes.pdf)


