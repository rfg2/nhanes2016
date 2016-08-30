# nhanes2016
Tips and tricks for using CDC's NHANES survey data
NHANESIII data in Stata
Unlike continuous NHANES (1999-2016), NHANESIII survey and linked mortality follow-up data are not available at cdc.gov as SAS transport files (easily read into Stata).There are several steps to loading the NHANES III text data files and saving them as permanent Stata datasets. To import NHANESIII data into Stata after downloading from CDC's website, use the instructions found in the NHANES tutorial at this link. An infile statement and data dictionary are required.
http://www.cdc.gov/nchs/tutorials/NH...ask3_III_c.htm
Example:
I need to create a Stata dataset with selected variables from the NHANESIII Adult.dat file with questionaire data for surveyed adults. I download the data file and codebook from the NHANESIII website at cdc.gov. Then I use Stata Do-file editor to create a data dictionary specifying the locations, names and width of variables. Then I run an infile statement to import the data to Stata. I check it versus the codebook and then save it as a Stata data set as the instructions at the link above described.

infile using "C:\Users\Yewande\Desktop\Research with Dr. Gillum\Spirometry and Mortality\Stata\Data file\NH3\adultxt2.dct", using ("C:\Users\Yewande\Desktop\Research with Dr. Gillum\Spirometry and Mortality\Stata\Data file\NH3\adult.dat")

dictionary{

_column(1)      seqn	%5.0f		"Sequence"

_column(1467)	hac1c	%1.0f		"Heart failure"

_column(1468)	hac1d	%1.0f		"stroke"

_column(1470)	hac1f	%1.0f		"chronic bronchitis"

_column(1471)	hac1g	%1.0f		"emphysema"

_column(1479)	hac1o	%1.0f		"other cancer"

_column(1561)	had1	%1.0f		"diabetes"

_column(1598)	hae1	%1.0f		"htn"

_column(1620)	hae7	%1.0f		"high cholesterol"

_column(1648)	haf10	%1.0f		"heart attack"

_column(1884)	hal1	%1.0f		"cough"

_column(1885)	hal2	%3.0f		"years of cough"

_column(1888)	hal3	%1.0f		"bring up phlegm"

_column(1889)	hal4	%3.0f		"years of phlegm"

_column(1892)	hal5	%1.0f		"shortness of breath"

_column(1893)	hal6	%1.0f		"wheezing"

_column(1897)	hal8	%3.0f		"hospital wheezing"

_column(1900)	hal9	%1.0f		"doctor/Er wheezing"

_column(1941)	hal20c	%1.0f		"pneumonia"

_column(2281)	har1	%1.0f		"100 cigarettes in life"

}
