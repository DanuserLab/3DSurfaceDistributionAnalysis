# Weems-Septin-Paper
This bundle contains code used in [**Blebs Promote Cell Survival by Assembling Oncogenic Signaling Hubss**](https://doi.org/10.1038/s41586-023-05758-6), *Nature*, 2023, 615, 517–525, written by Weems, A.D., Welf, E.S., Driscoll, M.K. et al. Additional information can be found in the Methods section of this paper.

**3D Surface Distribution Analysis** – post-processing MATLAB scripts designed to analyze signal distributions on and near u-Shape3D-generated cell surfaces.

- Earth Mover’s Distance – Analyzes distributions of fluorescence signal on u-shape3D-generated surfaces by measuring the earth mover’s distance along the surface  between the observed signal distribution and a homogenous distribution of the same signal.

- Surface Colocalization – Quantifies colocalization of two fluorescent signals on a u-shape3D-generated surface by calculating the Spearman’s rank correlation coefficients between the distributions. Significance is then approximated using a variation of Costes’ randomization in which one signal is randomized and the correlation is measured again, repeated 1000 times, returning the final fraction of randomized Spearman coefficients greater than the observed correlation (P-value). Because the sampling of local intensity of a surface signal through overlapping spheres (as done with u-Shape3D) produces a smoothing effect that leads to spatial autocorrelation, signal distributions are downsampled to below the level of spatial correlation to assure independence of data points. This is accomplished by selecting 200 random equidistant points on a cell’s surface before Costes’ randomization is performed on these points. To assure that this random selection does not bias the analysis, the process is repeated 10 times, with the resulting P-values averaged to a single mean P-value. If the mean P-value is less than 0.05 the colocalization of the tested signals is deemed significant.

- onionPeeler – Two scripts that measure fluorescence intensity in voxels near the cell surface. Relies on uShape-3D-generated surfaces to create tiff files of raw voxels within a set distance of the surface (for these scripts, intracellular voxels within 0.96 microns of the surface, or about 8 voxels deep). These two scripts analyze such datasets, returning either the number of near-surface voxels above a manually-measured cytoplasmic intensity, or the enrichment of fluorescence intensity within near-surface voxels compared to a homogenous distribution of all fluorescence signal within the cell.

**Timeseries Analysis** – Python code used to analyze septin and curvature dynamics in high-speed timelapse data. The code bundle currently lacks certain pre-processing steps (rigid/non-rigid registration, curvature/intensity measurement, and smoothing) that were performed using a large python library currently being developing into an independent software pipeline. This new software package will be submitted for publication in late summer of 2022 and posted in a new repository at that time. Pertinent code from this library is shared for transparent documentation of the analyses performed in the manuscript by Weems et al (see timeSeriesAnalysis Preprocessing.pdf). Upon release of the entire library, the present README.md file will be updated to reflect the availability of a fully functional pre-processing pipeline.

**Post-Processing Scripts** – MATLAB code that analyzes u-Shape3D output and returns various measurements used in the paper, such as surface intensity as a function of curvature, intensity as a function of distance from bleb edge, fraction of cell surfaces comprised of blebs, etc. 

## Danuser Lab Links
[Danuser Lab Website](https://www.danuserlab-utsw.org/)

[Software Links](https://github.com/DanuserLab/)
