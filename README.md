# Leukemia Classification Project

This project is dedicated to the classification of leukemia types based on gene expression profiles. It utilizes a dataset of gene expressions for patients diagnosed with different types of leukemia. The main objective is to build a predictive model that can accurately classify the type of leukemia from the gene expression data, trained on very small data.

## Dataset

The dataset used in this project is `Leukemia_GSE28497.csv`, which contains gene expression data for various leukemia types. The data is hosted at `https://sbcb.inf.ufrgs.br/data/cumida/Genes/Leukemia/GSE28497/`.

### Dataset Structure

The dataset includes the following columns:
- **sample**: The sample code of the patient (used as an index for the data).
- **type**: The type of leukemia diagnosed.
- **Gene_nam1, Gene_name2, ..., Gene_N**: Expression levels of thousands of genes.

### Dataset Class

A Python class named `Dataset` is used to manage the dataset. This class handles downloading the data (if not present), loading it into a Pandas DataFrame, and performing initial preprocessing including:
- Encoding the `type` column using label encoding.
- Retaining the sample code within the DataFrame without setting it as an index.

#### Usage

To use the `Dataset` class, ensure you have Python installed along with the Pandas library. Here is a basic example of how to initialize the dataset and access the data:

```python
from dataset import Dataset

# Initialize the dataset
dataset = Dataset()

# Access the processed DataFrame
data_frame = dataset.data

# Get the mapping of leukemia types
label_mapping = dataset.get_label_mapping()
print("Leukemia Type Mapping:", label_mapping)