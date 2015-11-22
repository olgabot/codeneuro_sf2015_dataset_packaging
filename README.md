# Dataset packaging @ CodeNeuro SF 2015

1. Introductions
	- Common problems/interests: 
		- Publishing datasets so they make sense to future people are available for several years
		- What are the common problems that people experience for packaging their data?
		- How do people acutally share their data?
2. [@olgabot](https://github.com/olgabot): packaging data in [`flotilla`](https://github.com/YeoLab/flotilla) using [`datapackages`](http://dataprotocols.org/data-packages/)
	- How to get hosting for sharing datasets?
		- Emailing a zip file ....
3. [@shoyer](https://github.com/shoyer): Packaging data in [`xray`](https://github.com/shoyer) using [NetCDF](http://www.unidata.ucar.edu/software/thredds/current/netcdf-java/CDM/)
	- Store data compressed as a small int with a scaling factor
	- Share dimensions between different matrices
	- How to share the data? Some centralized datsets
4. [@danlurie](https://github.com/danlurie) - how to standardize fMRI data? [Brain Imaging Data Structures](http://bids.neuroimaging.io/)
	- fMRI data of voxels (volume pixels)
	- Standardized data format - like a jpeg
	- Agreed upon headers
	- DICOM - every volume is a separate image
	- "volume" = one snapshot in time
	- Coming up with a standard of how subjects and time is named
5. [@sofroniewn](https://github.com/sofroniewn/) - [`tactile-coding`](https://github.com/sofroniewn/tactile-coding)
	- Data coming off the scope every second! (24 MB/s)
		- ~86GB/hour!
	- No clear standard. Ad-hoc JSON files of metadata
	- [Binder](http://app.mybinder.org/3165413014/tree) of several Jupyter notebooks that describe the code and data used with his paper
6. [@maxogden](https://github.com/maxogden) on the (Advanced scientific data format) [asdf](http://asdf-standard.readthedocs.org/en/latest/) data format for astronomy
	- Replaces FITS
	- Raw image of the sky, plus a "catalog" which is the interpreted data
	- Requirements:
		- Hierarchical representation in the same file as the image data
		- Open it in a program and get the metadata AND the raw data
	- [ASDF paper](http://www.sciencedirect.com/science/article/pii/S2213133715000645)
		- Really good background research (covers NETCDF, csv, etc)
		- Describe their data requirements
		- Use [YAML](http://yaml.org/) as their human readable format
		- ["Exploded form"](http://asdf-standard.readthedocs.org/en/latest/file_layout.html#exploded-form)
			- Allows random access of large files
		- [Source of the paper](https://github.com/spacetelescope/asdf-standard)
			- [Issue Tracker](https://github.com/spacetelescope/asdf-standard/issues)
		- Still 0.1.0
	- [Python implementation of ASDF](https://github.com/spacetelescope/pyasdf)
	- Also [SquashFS](http://squashfs.sourceforge.net/) compressed file system. Can read all the files without expanding it