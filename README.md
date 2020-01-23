# Optimization and Processing of Pandas DataFrames in Chunks for Low Memory Footprint

This is a guided project under Dataquest (DQ) where I demonstrated the processing of a Pandas DataFrame in chunks and selection of suitable data types to reduce its memory usage. Processing of datasets can encounter several performance issues such as long run times and code failures due to its file size and memory usage. I worked with a sample dataset from [Lending Club](https://www.lendingclub.com/), an American financial lending company that matches borrowers with investors. The dataset provided by DQ contained information on loans approved from 2007-2011. My aim in this project is to show the processing of the dataset using only 10 MB of memory and reduce its overall memory footprint as a Pandas DataFrame.

To process the dataset with limited memory and optimize its memory usage, I performed the following:

* Explored the first 5 rows of the dataset and determined the number and pre-assigned data types of the columns
* Selected an appropriate `chunksize` of data (number of rows) that has a memory usage of less than 5 MB (50% of 10 MB)
* Inspected the consistency of pre-assigned data types in the columns per data chunk
* Parsed the string type columns that contain dates as values and converted them into `datetime` type
* Determined the string type columns that contain less than 50 unique values and converted them into `category` type
* Removed the rows with missing values and compared the total number of rows before and after modification
* Determined the string type columns suitable for cleaning and converted them into a numeric type
* Optimized the data type of numeric columns, e.g. from `float64` to another `float` type of lower memory footprint 
* Determined the numeric type columns that have no missing values for possible conversion to `integer` or `float` of low memory usage

The optimization procedure has the following findings:

* A `chunksize` of 3000 rows has a memory usage of ~ 5 MB which is appropriate for a low-memory environment of 10 MB
* Removal of rows with missing values retains more than 90% of the original information from the dataset
* Data cleaning and assignment of appropriate data types on the columns reduce the memory footprint of the Pandas DataFrame by 67.5%

For more details, please see the `Project6.ipynb` notebook and the `loans_2007.csv` file above.
