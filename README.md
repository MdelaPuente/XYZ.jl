# XYZ.jl
A Julia package to read MD trajectories in xyz format

This package is heavily inspired by the one developed by Michael von Domaros (`mvondomaros`) for reading dcd
formatted MD trajectories (see their [repository](https://github.com/mvondomaros/DCD.jl)) and by the (private) 
work of Axel Gomez.
It only works for trajectories with a constant number of atoms (can not be used for GCMC simulations for example) 
but the atoms can be in different orders in different frames.


## Installation

```julia
pkg> add https://github.com/MdelaPuente/XYZ.jl
```

## Usage

```julia
using XYZ

xyz = load_xyz("foo.xyz")

na = natoms(xyz)  # Get the number of atoms.
nf = nframes(xyz) # Get the number of frames.

for frame in xyz  # Iterate over each frame.
  r = positions(frame)  # Get an array of Float64 of all current positions with dimensions (3, na).
  a = atomnames(frame)  # Get an array of String of the names of atoms in order of the current frame
  
  # Do stuff.
end
```

Happy coding and big thanks to `mvondomaros` and to Axel Gomez for their work!
