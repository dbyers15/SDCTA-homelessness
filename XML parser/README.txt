READ ME

990 - error check.ipynb : This is the running code for the Phil dataset. The code pulls 990 information via EINs and outputs a dataset. It includes the manipulation to fix errors, extract missing information from the 990 Manual Pull, and expand every fiscal year by month.

990 Manual Pull - Cleaned EIN List.csv : EIN list of the manually pulled EINs
990 Manual Pull - Tax End Date.csv : Contains the 990 manually pulled data, as well as an additional column that contains manually inputted the Tax End Dates for the EIN_YEAR values that weren't extracted via XML

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