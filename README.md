# TRAPL

Track planning of local congestion for global routing
Tool name: 	wiscTraPL
Organization:	WISCAD Lab in University of Wisconsin Madison
Author: 	Daohang Shi (shidaohang1990@gmail.com) and Azadeh Davoodi (adavoodi@wisc.edu)
Date: 		August 2017
NSF Award # 1608040 https://www.nsf.gov/awardsearch/showAward?AWD_ID=1608040&HistoricalAwards=false

Usage:
./wiscTraPL
	-design_info                : input file of all info about the design
	-tar_gcell_util (optional)  : wiscTraPL output file of gcell utilization
	-tar_gcell_tov  (optional)  : wiscTraPL output file of gcell track overflow

-design_info: 
	After sourcing .lef, .def and .v files in Mentor Graphics Olympus SoC, we can run some physical design steps and then export the DB information needed by wiscTraPL. The Tcl script to export the DB information can be found in http://homepages.cae.wisc.edu/~adavoodi/.  

-tar_gcell_util:
	Optional flag to export normalized track utilization for all global cells.  The file will begin with header comments and dimension information of global routing grid graph.  For example, a design has 2 routing layers, each of which has 3x4 global cells.  The output file will be as below.
>>>
# wiscTraPL output file
dimX : 20
dimY : 30
dimZ : 3

0.8 0.8 0.6
0.6 0.7 0.5
0.8 0.8 0.6
0.5 0.7 0.6

0.8 0.8 0.6
0.6 0.7 0.5
0.8 0.8 0.6
0.5 0.7 0.6
<<<

-tar_gcell_tov:
	Optional flag to export normalized track overflow for all global cells.  See -tar_gcell_util for the file formats.
