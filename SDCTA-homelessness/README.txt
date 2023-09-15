READ ME

BACKGROUND

The purpose of this Homelessness project is to create a dataset that gathers data pertaining to any homelessness services within San Diego County. The funding comes from four sectors: City, County, Government, and Philanthropic funding. Once we have this whole dataset, we can calculate the total amount of money that has been contributed to homelessness services in San Diego County within recent years.

The finetuning script is currently being used on City data with the hopes of having the accuracy to use on the County data. With the city data, we have folders of contracts organized by each city within the county and contracts of organizations that get funding from the city. From each contract, we are interested in finding "Grantor", "Grantee", "Program", "Date", "EndDate", "Amount", "Funding Source", "text_id" (the text file name).

With this code function for the cities and eventually, hopefully, the county, the goal is to be able to expand this beyond San Diego County to help this homelessness issue everywhere. This is a large investment of time, but taking out the data manually has proved to be time-consuming and taxing.


HOW IT WORKS

Fine-tuning is a machine learning technique where a pre-trained model is further trained on a specific task or dataset to adapt its knowledge and parameters for improved performance on that task. 
 
*finetuning_script.ipynb* uses the finetuning feature of OpenAI to take training data in the form of prompt-completion pairs exported inot a json file. For this, our prompt is the contract's text file and its completion is the outputted *Grantor, Grantee, Program, Date, EndDate, Amount, Funding Source, text_id* that was manually pulled from the contracts. Then, we can input the testing files and compare the output to the manually-pulled outputs to see the accuracy.


INCLUDED FILES / SCRIPTS

*finetuning_script.ipynb* : Uses the manually added documents in the folders to prepare the trained data for fine-tuning and testing it.

all_text_docs: contains all the training / testing files

sorted_files: DON'T USE THIS WITHOUT FIXING - contains folders for the training and testing files, has major encoding issues right now

test_txt: testing files to input into finetuning code


DATASETs

data.csv: the outputted dataset from the finetuning script after it's been manipulated to fit a dataframe

dir_finetuneTrain0608.csv: the prompt-completion pairs for the training data

dir_finetuneTrain0608_prepared.jsonl: the dir_finetuneTrain0608.csv exported as a JSON file for fine-tuning

ML Workflow - Data.csv: The manually pulled data from all these files containing all the necessary columns that we used to know which files are Train/Test and to compare for accuracy.
