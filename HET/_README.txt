The unpacked directory includes a batch of LRS2 spectra. The objects are cataloged in the file catalog_<qualifier>.lis.

LRS2 data file names have the following form

spectrum_YYYYMMDD_nnnnnnnnn_expEE_arm,fits

where YYYYMMDD is the date of the observaiton

      YYYY = 4-digit year
        MM = 2-digit month
	DD = 2-digit day

nnnnnnnnn = serial number of the observation for that program, usuall 0000000nn

expEE = exposure number, usually exp01

arm = uv,orange (for LRS2-B) red,farred (for LRS2-R)

We always get four files for each observation, one for each arm of the LRS2. But, if we only observed with LRS2-B or LRS2-R, two of the files will have a meaningful spectrum and the other two will have zeros.

Each FITS file has 6 arrays:

ROW1    = 'wavelength' (Å, linear scale)
ROW2    = 'F_lambda'  (ergs/s/cm2/Å)
ROW3    = 'Sky_lambda' (sky spectrum already subtracted)
ROW4    = 'e_F_lambda' (error bar on final object F_lambda)
ROW5    = 'e_Sky_lambda'  (error bar on sky spectrum F_lambda)                                                      
ROW6    = 'response'                                                            

The calibrations were carried out by the Panacea pipeline, which is described at this GitHUB page: https://github.com/grzeimann/Panacea/

Note that corrections for absorption in the Earth's atmosphere have NOT been applied. These include corrections for continuous absorption and scattering and corrections for discrete absorption bands from molecular oxygen and water vapor. 
