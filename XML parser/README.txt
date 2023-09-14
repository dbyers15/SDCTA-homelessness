READ ME

BACKGROUND

The homelessness project is a compilation of city, county, government, and philanthropic data that gives us an exact amount that has been spent on homelessness within San Diego.

For this branch of this homelessness project, compiling the philanthropic data will help identify how much money is put towards homelessness services in San Diego and the sources of funding for each nonprofit organization.
The *Philanthropic Homelessness Data Pull* is a script that pulls data from ProPublica, a tax site that uploads tax returns for nonprofit organizations, searchable through the organization's unique EIN. Compiling this data together, we can get the total philanthropic dollars for homelessness within recent years given that we have the full EIN list.


INCLUDED FILES / SCRIPTS

Philanthropic Homelessness Data Pull.ipynb : This is the running code for the Phil dataset. The code pulls 990 information via EINs and outputs a dataset. It includes the manipulation to fix errors, extract missing information from the 990 Manual Pull, and expand every fiscal year by month.
- Run the grabber(eins) function to pull the inputted EINs from ProPublica
- Clean up the data (drop the NaN values, create EIN_YEAR values)
- Export to csv file
- Check for errors using find_errors() and reinput EINs that were outputted into grabbers with errors = True
- Use replace_corrected_data_and_standardize() function to replace errored data with corrected data from the grabber(errors=True) call
- Follow code to fill in any missing data that was included in the Manual Pull or most recent dataset (Phil Dataset.csv)
- Use distribute_values_fiscal_year() function to expand by month

Master EIN List - Master.csv : Updated csv file, should be consistently updated with new EIN inputs

(old EIN lists)
990 Manual Pull - Cleaned EIN List.csv : EIN list of the manually pulled EINs
990 Manual Pull - Tax End Date.csv : Contains the 990 manually pulled data, as well as an additional column that contains manually inputted the Tax End Dates for the EIN_YEAR values that weren't extracted via XML



DATASETS

full_table.csv : raw dataframe from 990 XML pull with missing rows
no_errors.csv : cleaned dataframe from 990 XML pull

info_no_errors.csv :
- only has the EINs after correcting the errors from the no_errors.csv
- needs to replace the current rows in no_errors.csv

EIN_dataset.csv :
- corrected errors by replacing values of no_errors.csv with info_no_errors.csv

not_scraped.csv : manually pulled data (from the 990 Manual Pull - Tax End Date.csv) for the EIN_YEAR values that didn't have a 990 XML file

Phil Dataset.csv : combined EIN_dataset.csv and not_scraped.csv

Phil Dataset - Analysis.csv : Phil Dataset.csv expanded by month for the fiscal year with equally divided financial values.