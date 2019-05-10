# Segmentation examples
Here we provide code accompanying our guide to psycho-behavioral segmentation for programs in global health (link to paper will be added when available). 

Figure 2 in the paper shows some simulated examples of k-means and hierarchical clustering, and attempts to illustrate how idealized data differs from a more realistic data set, to help researchers set expectations and evaluate solutions found. 

![Idealized segmentation](.static_images/kmeans_idealized.png)
![Idealized segmentation](.static_images/kmeans_realistic.png)

The code to generate these graphs can be found in the notebook [show_clustering_examples.ipynb](show_clustering_examples.ipynb) in this repository. The data simulation, clustering, and plotting is performed in the supporting script called [segmentation_helpers.R](segmentation_helpers.R). Feel free to copy the code to your own computer and play around by generating different shapes of data and seeing how the clustering algorithms perform (instructions below).

In addition to what is in the paper, the notebook contains:

1. so-called "elbow plots" for the idealized and realistic data, helping analysts determine the appropriate number of clusters
1. Example of data where k-means fails, and how an alternative clustering algorithm (gaussian mixture model) can accurately cluster these data

In the future we might add additional examples and supporting code for the benefit of teams performing segmentation. 

---

## Running this code on your own computer

1. [Install R](https://cran.rstudio.com/).
1. [Install RStudio](https://www.rstudio.com/products/rstudio/download/), which is software that makes it much easier to work with R.
1. Download the files in this repository to your computer using [git](https://guides.github.com/introduction/git-handbook/#basic-git). If you're not familiar with git, just press the green button on the right that says "Clone or download" and press "Download ZIP" and unzip on your computer.
1. Open up RStudio  and in the file navigation pane, navigate to the unzipped folder and click on the file `segmentation_helpers.R`. You now see the code that will generate data, fit clusters to them, and plot the clusters.
1. Run this file (called "sourcing" in R parlance, top right of the code editor) to make the functions available. The first time you do this it will install some additional R packages.
1. In the console copy and paste the following to check everything is working:

```
df = GenerateClusteredData(
  cluster.centres.x = c(1, 2, 3),
  cluster.centres.y = c(1, 2, 1),
  cluster.n         = c(150, 150, 150),
  cluster.sds.x     = c(0.2, 0.2, 0.2),
  cluster.sds.y     = c(0.2, 0.2, 0.2)
)
GenerateAndPlotClusters(df, plot.label = 'idealized', do.dendrogram = FALSE)
```

And you should see a graph like this:
![Idealized segmentation](.static_images/kmeans_idealized.png)

### Running the Jupyter Notebook
You can also run [the Notebook](show_clustering_examples.ipynb) in the browser on your computer. Setting this up is a little more involved as it requires Python as well as an R kernel to be installed for the Notebook. Here is the [official Jupyter installation guide](https://jupyter.org/install), and [here is how to install the R kernel](https://irkernel.github.io/installation/) so you can use R in Jupyter Notebooks.

You can then start your Notebook server by opening a terminal, navigating to the folder on your computer with this repository, and typing

```
jupyter-lab
```

## License
We encourage you to use the code for any purpose you like under the permissive [MIT License](http://mit-license.org). 
