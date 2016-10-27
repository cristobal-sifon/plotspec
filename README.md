# plotspec
Tool for plotting 1d and 2d spectra

----

`plotspec` is a simple, stand-alone, spectral plotting tool. It allows the display of one or several 1d spectra below the corresponding 2d spectrum, with both plots matched in wavelength. It can also display the location of emission and/or absorption lines that can either be supplied by the user or taken from the default set incorporated in the code. Additionally, these lines can be redshifted by a user-supplied value. At the bottom of this page you'll find examples of an emission-line and an absorption-line example spectra. You can download the data that was used to create the plots shown by clicking in the figures. 

#### Usage:
    plotspec [-h] <parameter1>=<value1> <parameter2>=<value2> ...


#### Parameters: 

  * `file1d` (type: string)  
If ``fileroot`` is provided (see below), then this is the suffix of the 1d spectrum file, with root `fileroot`. Otherwise, this is the full name of the 1d spectrum. A ".fits" extension is automatically added to the end of the filename, if not given. 

#### Optional arguments:

  * `file2d` (type: `string` &mdash; default: `' '`)  
If `fileroot` is provided, then this is the suffix of the 2d spectrum file, with root `fileroot`. Otherwise, this is the full name of the 2d spectrum. A ".fits" extension is automatically added to the end of the filename if not given. If this is parameter not provided, only the 1d spectrum is displayed.
  * `fileroot` (type: `string` &mdash; default: `''`)  
A root common to the 1d spectrum and the 2d spectrum filenames. If `fileroot` is provided but not `file1d` or `file2d`, then it is assumed that `file1d=fileroot+'e'` and `file1d=fileroot+'s'`.
  * `z` (type: `float` &mdash; default: `0`)  
The redshift to which the lines will be moved, i.e. this should be the redshift you expect the source to be at. 
  * `cz` (type: `float ` &mdash; (default: `0`)  
The cosmological velocity, `c*z`, to which the lines will be moved (if `z` is provided, this entry is ignored). Note: `c=299792.458 km/s`. 
  * `dv` (type: `float` &mdash; default: `500`)  
The width of the lines to be shown, in `km/s`. 
  * `figtitle` (type: `string` &mdash; default: `''`)  
A title to print in the plot (e.g. the name of the object). Must not contain spaces
  * `linefile` (type: `string` &mdash; default: `''`)  
Text file containing the lines that will be plotted with the spectrum. The format of the file is two columns (space-or tab-separated), the first being the rest-frame wavelength and the second being the name of the line. Lines can be commented with the `#` character. If the file is not provided, a default set of lines including the most common ones (from ~100 to ~700 nm) will be displayed. 
  * `tickspace` (type: `int` &mdash; default: `500`)  
Separation between ticks in the plot, in Angstrom. 
  * `vmin` (type: `float`)  
Lower limit, in counts, used for the colorscale. If not provided it is automatically calculated as in DS9's `zscale`.
  * `vmax` (type: `float`)  
Upper limit, in counts, used for the colorscale. If not provided it is automatically calculated as in DS9's `zscale`.
  * `contrast` (type: `float` between `0` and `1` &mdash; default: `0.6`)  
The contrast of the 2d image, as in DS9. 
  * `thresh` (type: `float` &mdash; default: `20`)  
Threshold, in units of the counts standard deviation, to remove bad pixels from the 1d spectrum. Make it higher if you expect strong emission lines. Only works for very high pixels (as opposed to very negative ones). 
  * `linefill` (type: `float` between `0` and `1` &mdash; default: `0.8`)  
Greyscale color of the shading around each line (with width equal to `dv`), where `0` is black and `1` is white. 
  * `lheight` (type: `float` between `0` and `1` &mdash; default: `0.2`)  
Relative height at which to place the names of the lines, with respect to the maximum value of the spectrum. 

----

### Examples


----

(c) 2012-2016 Cristóbal Sifón
