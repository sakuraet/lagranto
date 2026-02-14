# lagranto

## personal directory 

wd: /jet/home/stakahas/lagranto_runs 

cd ~/lagranto_runs/ 
cd /ocean/projects/ees210020p/hsun3/LAGRANTO/LAGRANTO_model_Simons

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