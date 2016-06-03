# THOMAS: Thalamus-Optimized Multi-Atlas Segmentation
Segmentation of the thalamus into 12 nuclei using the white-matter-nulled image contrast and PICSL's joint label fusion.  Note that this requires prior/ and template.nii.gz, provided elsewhere.

# Installation
- git clone https://github.com/sujason/thomas.git
- Extract THOMAS-priors.zip to thomas/
- python require.py
- IMPORTANT: there is a bug in ANTs/Examples/antsJointFusion.cxx when using a mask, this may require rebuilding ANTs.
	- One way: git clone https://github.com/sujason/ANTs.git, then use cmake to build.
	- Another way: git clone https://github.com/stnava/ANTs.git, then replace ANTs/Examples/antsJointFusion.cxx with thomas/antsJointFusion.cxx, then use cmake to build.

# Usage
- python THOMAS_v0.py -h
- Example: python THOMAS_v0.py -p 4 --tempdir ants image.nii.gz ./ ALL
	- tempdir is often useful in case something goes wrong, you can resume from previous attempts.