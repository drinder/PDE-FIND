The code and manuscript in this repository have a few errors worth noting that affect results:
1) Model selection uses the $\ell^2$ norm rather than the squared $\ell^2$ norm is shown in the manuscript.  This was an oversight in the paper and has been left as is in the code.
2) TrainSTRidge initially passed the full data to STRidge rather than training partition of data as shown in the supplemental materials.  This has been fixed.
3) PolyDiff initially used an even number of points.  This was not an error, per se, but was written unintentionally and is non-standard.  It has since been changed to a symmetric set about the point being differentiated.  Errors seem to be slightly improved, though change is minimal.

The code has been updated to run using Python 3.  However, we stress that this repository is not actively maintained and there exist many more modern approaches that offer far better performance.  In particular, an improved implementation of PDE-FIND and related methods may be found in the [PySINDy package](https://github.com/dynamicslab/pysindy). See notebook 10 in PySINDy/examples.  The most significant barrier to the application of PDE-FIND is the sensitivity of numerical differentiation.  To this end, we strongly suggest the interested reader look into more recently developed weak forms of system and PDE identification as these lack the sensitivity to differentiation present in the current work.