# lagranto

## links 

hongwei's github (python scripts):
https://github.com/hongwei8sun/LAGRANTO/tree/main/Python_script_paper2

## commands 

less : reads file do q to quit
ncdump : ncdump allows you to read netcdf files
- ncdump -h P20000101_00 
grep : searches text inside files
- grep -R "caltra" -n .
  - -R searches recursively in all directories 
  - caltra is the string im looking for 
  - n is print the line number

## directories

wd: /jet/home/stakahas/lagranto_runs 
p files:  /ocean/projects/ees210020p/hsun3/LAGRANTO/LAGRANTO_P_files 
model: /ocean/projects/ees210020p/hsun3/LAGRANTO/LAGRANTO_model_Simons
bashrc: /jet/home/hsun3/bashrc_LAGRANTO

cd ~/lagranto_runs/ 
cd /ocean/projects/ees210020p/hsun3/LAGRANTO/
LAGRANTO_model_Simons

## startf.final 

coordinates of where to start?

## startf.final_backup 

unsure what this is, there's a lot more coordinates in here compared to startf.final

## srun2000_01_01.slum

slurm script is what runs everything?

## P files 

seems to be meteorlogical data (pretty big) 

## instal.csh 

csh files: associated w/ C shell (unix shell) that provides a cmd line interface w/ the os 

It’s a build/install script written for the csh shell (#!/bin/csh).

It can do things like:
- load compiler + NetCDF modules
- compile LAGRANTO libraries (lib/*.a)
- compile core executables (especially caltra)
- compile extra utilities (“goodies/tools”)
- create the bin/ symlinks (so commands like caltra work)
- “clean” builds (delete compiled outputs)
- pull/update code from a repository (SVN path is in there)

So: it’s for maintaining the software, not for running simulations. 

## IMPORTANT 

caltra 20000101_00 20000109_00 startf.test traj_20000101.1 -o 60 -j
- caltra : LAGRANTO trajecory solver 
- 20000101_00 : start time 
- 20000109_00 : end time 
- startf.test : injection locations 
- traj_20000101.1 : output trajectory files 
- -o 60 : output every 60 mins 
- -j : job mode