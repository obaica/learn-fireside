# Cutoff convergence vs Forces

## Convergence test

Similarly to the [previous exercise](../1_ecut_vs_etot), we are going to calculate the convergence on the energy cutoff for the PWs with respect to an output parameter of the code.  
In this case we are going to look at the forces acting on an atom calculated using the [Hellmann-Feynman theorem](https://en.wikipedia.org/wiki/Hellmann%E2%80%93Feynman_theorem).  
In order to actually have forces on the atoms, we have to move one atome slightly in order to break symmetries, otherwise all the forces would be 0. 

## Example exercise

1. Download the [provided input files](../files/NaCl.scf.in)
2. Copy or link the pseudopotential files for Na and Cl inside a folder named ```pseudo``` in the same path of the input file
3. Modify the input file to use a 4x4x4 grid and shift one of the two atoms along the ```z``` dirction by 0.05
4. Run the code pw.x from terminal using the command ```pw.x < Na.scf.in > Na.scf.out```
5. Collect the value of the forces acting on the two atoms (you expect to have the x and y components equal to 0 and that fz_Na = - fz_Cl).
  The lines containing this information in the output file will look like this:  
  ```atom    1 type  1   force =     0.00000000    0.00000000    0.02365046```
6. Increase the value of ```ecutwfc``` by 10 Ry and the value of ```ecutrho``` by 80 Ry in the input file.
7. Repeat points 4 through 6 until a convergence of 10 meV/Angstrom is achieved.

TIP: You can modify the [bash script](../files/script.sh) provided in this repository to automate this process or write your own script in any scripting language.

[BACK TO INDEX](../README.md)