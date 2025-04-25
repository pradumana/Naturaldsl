#NaturalDSL: Documentation
Overview
NaturalDSL is a next-generation, human-first natural programming language tailored for data science. Designed to provide intuitive and human-readable code, NaturalDSL abstracts away the complexity of traditional programming languages while still offering the power and flexibility needed for professional data science tasks.

The language integrates seamlessly with Dask, Pandas, Numpy, Seaborn, and Matplotlib, making it a comprehensive tool for data analysis, visualization, and manipulation.

Core Features:
Human-Readable Syntax: Designed to use natural language constructs for common data science tasks.

Data Manipulation: Supports loading, cleaning, transforming, and aggregating data.

Data Visualization: Offers intuitive plotting methods with Seaborn and Matplotlib.

Parallel Computing: Efficiently process large datasets with Dask’s parallel computing capabilities.

Extensibility: Easily extendable through plugins and external libraries.

Code Autocompletion & AI Integration: The built-in AI suggests code completions for common data science tasks.

Batch Processing: Ability to handle large-scale datasets with ease.

Getting Started
System Requirements
Python 3.7 or higher

Pip for managing packages

Internet connection (for installing dependencies)

Installing Dependencies
To get started with NaturalDSL, install the required dependencies using the provided requirements.txt file:

Clone the repository (if you haven't done so):

bash

git clone https://github.com/pradumana/naturaldsl.git
cd naturaldsl
Install the required dependencies:

bash

pip install -r requirements.txt
This will install all necessary libraries like Dask, Pandas, Seaborn, Matplotlib, and Numpy.

Installing from PyPI (Optional)
If you wish to install the package globally via PyPI:

bash

pip install naturaldsl
Project Structure
Here’s the folder structure for the project:

text

naturaldsl/
│
├── natural_dsl_interpreter.py         # Main interpreter code
├── cli.py                             # Command Line Interface for interaction
├── requirements.txt                   # Dependency list
├── setup.py                           # Package setup
├── pyproject.toml                     # Project metadata and build system
├── LICENSE                            # License file
└── README.md                          # Project overview and instructions
CLI Usage
NaturalDSL provides a command-line interface (CLI) to interact with the data and perform operations on it. The CLI is designed to make data science tasks simple and intuitive.

Basic Command Syntax
bash

naturaldsl [COMMAND] [OPTIONS]
Common Commands
Load a dataset: Load CSV or Parquet data files into the interpreter.

bash

naturaldsl load [filename.csv|filename.parquet]
Example:

bash

naturaldsl load data.csv
Save data: Save the modified dataset to a CSV or Parquet file.

bash

naturaldsl save [filename.csv|filename.parquet]
Example:

bash

naturaldsl save cleaned_data.parquet
Data Cleaning:

Drop missing values:

bash

naturaldsl drop_missing column_name
Fill missing values with a constant value:

bash

naturaldsl fill_missing column_name value
Data Transformation:

Rename columns:

bash

naturaldsl rename old_name new_name
Sort data by a column:

bash

naturaldsl sort column_name ascending
Convert data types:

bash

naturaldsl convert column_name datetime
Group & Aggregate:

Group by a column and apply an aggregation:

bash

naturaldsl group_by column_name sum
Data Visualization:

Generate a bar plot:

bash

naturaldsl plot_bar column1 column2

Generate a scatter plot:

bash

naturaldsl plot_scatter column1 column2

Example CLI Session:

bash

naturaldsl load data.csv
naturaldsl drop_missing age
naturaldsl sort age descending
naturaldsl plot_bar age count
naturaldsl save cleaned_data.parquet

Advanced CLI Features

Plot Customization: You can adjust the appearance of plots (e.g., colors, labels, titles) directly from the CLI.

Multiple Command Chaining: Combine multiple commands in a single line for a more efficient workflow.

bash

naturaldsl load data.csv && naturaldsl drop_missing age && naturaldsl plot_scatter age salary
Python API Usage
For those who prefer using NaturalDSL within Python scripts, the package offers an easy-to-use API.

Basic API Workflow
python

from natural_dsl_interpreter import NaturalDSLInterpreter

# Initialize the interpreter
interpreter = NaturalDSLInterpreter()

# Load a dataset
interpreter.load("data.csv")

# Perform some transformations
interpreter.fill_missing("age", 0)
interpreter.rename("old_column", "new_column")

# Create a plot
interpreter.plot_bar("age", "salary")

# Save the transformed data
interpreter.save("processed_data.csv")
Available Methods
load(filename): Loads data from a CSV or Parquet file.

python

interpreter.load("data.csv")
save(filename): Saves the current dataset to a CSV or Parquet file.

python

interpreter.save("output_data.parquet")
drop_missing(column_name): Drops rows with missing values in a specified column.

python

interpreter.drop_missing("age")
fill_missing(column_name, value): Fills missing values in a specified column with a given value.

python

interpreter.fill_missing("age", 0)
rename(old_name, new_name): Renames a column.

python

interpreter.rename("old_name", "new_name")
sort(column_name, ascending=True): Sorts the dataset by a column, either in ascending or descending order.

python

interpreter.sort("age", ascending=False)
convert(column_name, dtype): Converts a column to a specified data type (e.g., datetime, number).

python

interpreter.convert("date", "datetime")
group_by(column_name, agg_function): Groups data by a column and applies an aggregation function (sum, mean, count).

python

interpreter.group_by("age", "sum")
plot_ methods*: Generate various types of plots using Seaborn and Matplotlib (e.g., plot_scatter, plot_bar, etc.).

python

interpreter.plot_scatter("age", "salary")
Extending NaturalDSL
Creating Custom Functions
You can extend NaturalDSL by adding custom functions for your specific use case. Custom functions can be defined in separate Python modules and then registered with the interpreter.

Example:

Create a custom function:

python

def custom_mean(dataframe, column):
    return dataframe[column].mean()
Register the function:

python

interpreter.register_function("custom_mean", custom_mean)
Using Plugins
NaturalDSL allows you to create plugins to extend the functionality, whether it’s adding new plotting capabilities, data sources, or even custom algorithms. You can load and use plugins via the CLI or Python API.

Contributing to NaturalDSL
We welcome contributions from the community! Whether it’s bug fixes, new features, or documentation improvements, we encourage you to participate.

How to Contribute
Fork the repository on GitHub.

Clone your fork locally:

bash

git clone https://github.com/your-username/naturaldsl.git
Create a new branch:

bash

git checkout -b feature-branch
Make your changes and commit them:

bash

git commit -m "Description of changes"
Push your changes to your fork:

bash

git push origin feature-branch
Open a pull request to merge your changes into the main repository.

License
NaturalDSL is licensed under the MIT License. See the LICENSE file for more details.

Contact
For more information, or if you have questions, please contact us at:

Email: prdmn.shrm@gmail.com


