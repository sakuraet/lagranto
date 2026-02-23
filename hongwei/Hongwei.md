This file is used to help people understand our model output files.
For any questions, please reach out to Hongwei Sun (hongwei_sun@g.harvard.edu)


#-------------------------------------------------------------------------------
(1)
1-year input data (P files in NetCDF) is provided, with a name format: Pyyyymmdd_hh
These P files are derived from the ERA5 (with 137 model levels) data, mainly including variables of U, V, W, surface pressure, and T.

(2)
All model output files are text files following the name format: traj_yyyymmdd.1
yyyymmdd refers to the injection date (year, month, day).
For example, traj_20000101.1 means that this file contrains trajectories/locations of all particles that are injected on Jan 1, 2000.


#-------------------------------------------------------------------------------
Inside each model output file:

In the first line: Reference date refers to the injection time (yyyymmdd_hhmm). Time range means the total simulating time (i.e., 10 years)


###
There are four columns for the data: time [hour], lon [deg], lat [deg], and p (pressure [hPa])
The data in each row is telling you the location (lon, lat, p) of the injected particle when the particle is injected (time) hours later

For example:

in the line of 6, the data is "    0.00     0.00  -30.00   100", which is corresponding to (time, lon, lat, p)
Because time=0.0, this line indicates the initail injection location, which means the particle is injected at lon=0, lat=-30, p=100 hPa at 20000101_0000 (yyyymmdd_hhmm).

in the line of 7, the date is "   24.00    18.84  -33.77   109", which is telling you that 24.00 (time) hours after injection, the particle is located at lon=18.84 deg, lat=-33.77 deg, p=109 hPa.


###
Each particle's initial injection location can be found by searching the line with time=0.00


#----------------------------------------------------------------------------------
People can use python to read our model output file. Here are some reference python codes in the following:
        # read original data from traj files
	Year = "2000"
	month = "01"
	day = "01"
        filename = "traj_"+Year+month+day+".1"
        file1 = open(directory+filename, 'r')
        Lines = file1.readlines()
	for line in Lines:
		values = line.split()
		time = float(values[0])
		lon = float(values[1])
		lat = float(values[2])
		pressure = float(values[3])