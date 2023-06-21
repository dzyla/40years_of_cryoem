"#40Years_of_CryoEM
Abstract embeddings of cryo-EM-related manuscripts from PubMed and bioRxiv

I utilized the code from this repository to create slides for the 3DEM GRS presentation.
How to use

1. First, retrieve the data from PubMed and bioRxiv using two separate notebooks. This process will generate two folders: PubMed and bioRxiv. These folders will contain the JSON files that store the manuscript metadata. Downloading from PubMed operates at a rate of approximately one file per second, while bioRxiv takes a bit longer.
2. Switch to the 'plot_abstracts.ipynb' notebook. Before running this notebook, ensure you have installed all the necessary dependencies.
3. Execute the cells in a sequential manner. Initially, the notebook will load and merge the JSON files into a pandas dataframe. Afterward, the data will be cleaned, removing duplicates and eliminating certain non-related early manuscripts. Please note that I have not conducted a thorough pruning of the abstracts, so it is probable that many abstracts do not pertain to the cryo-EM field.
4. Once the final dataframe is ready, the embeddings will be computed as a 768-dimensional tensor. This step is highly computationally intensive and is best performed with CUDA.
5. UMAP is employed to reduce the dimensionality of the data and separate the abstracts effectively.
6. Clusters are generated based on UMAP. This process is purely for visualization purposes. HDBscan yields the best results, but there remains a significant number of outliers (labeled as -1).
    Seaborn and Plotly (interactive) are utilized to generate the plots.

Essentially, by modifying the keywords in the PubMed and bioRxiv notebooks, this technique can be applied to plot abstracts from any other field. Enjoy!
