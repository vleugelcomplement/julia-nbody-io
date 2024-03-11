# julia-nbody-io

Julia is modern concise dynamic language with a focus on number crunching and good-quality data analysis libraries.  This makes it a appropriate choice for working with N-body simulation snapshots. To do something with a snapshot you'll need to read it first. 

## Background
The 'snapshot reading' land (as far as I know) looks as following:
- [MERA](https://docs.juliahub.com/General/Mera/stable/) can read RAMSES snapshots and be extended for any desired analysis;
- [GadgetIO](https://github.com/LudwigBoess/GadgetIO.jl) reads/writes Gadget2 binary snapshots;
- [HDF5](https://juliaio.github.io/HDF5.jl/stable/) can be used to read Gadget4 (see https://github.com/delos/gadget4-tools for inspiration);
- [AstroPlot](https://docs.juliahub.com/General/AstroPlot/stable/) can apparently also read something.

## Goal
Low-level format-agnostic Julia package that can just read most of the simulation snapshots.

## How?
My initial idea is to try to wrap [unsio](https://gitlab.lam.fr/infrastructure/unsio) C++ library and see how far we can get this way. I have a half-written read-only wrapper that can handle NEMO snapshots, but it is not yet tested on anything serious. Unsio also have various of stability and performance issues, therefore the right approach might be to do everything in Julia from the start. I'm open to discussion.
