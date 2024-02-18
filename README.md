# arXiv Hep-Ph Citation Network Analysis
The codebase is divided into 5 folders
- **Graph_Dump** - This contains the graphml files for the network after preprocessing and also after applying Louvain and Label Propagation. The Louvain and Label Propagation lables are accessible as a vertex property map in graph_tool after importing the graphml file. They will be accessible under the names "label_comms" and "louvain_comms". See Preprocessing.ipynb and Static_Community_Analysis.ipynb for more information.
- **Images** - This contains 3 folders,
    - **Comm_Paper_Tables** - Which contains the annotated arXiv API data images and the original arXiv API data images.
    - **Community_Analysis_Plots** - Which contains plots on the static network in static and plots on the temporal network in Temporal. Temporal has sub folders for each algorithm.
    - **Graphs** - Which contains graphs for exploratory graph analysis in Basic_Analysis and graphs for temporal community detection analysis in Temporal_Analysis.
- **Label_Dumps** - This contains 2 folders,
    - **Original_Community_Labels** - Which contains the community labels per node found by the various algorithms. Each can be loaded into python using pickle. The data is a list of lists, where each list in the main list contains community labels per node as an integer for that snapshot.
    - **Temporal_Community_Sets** - Which contains the community sets after every snapshot as found by the various algorithms. Each can be loaded into python using pickle. The data is a list of lists, where each list in the main list contains a tuple of 2 elements, the first being the community label, and the second being a set containing the indexes of the nodes belonging to that community.
    - Why did I use 2 different formats? I don't know. I wish I did.
- **Notebooks** - This is simple, it just contains Jupyter Notebooks for each part of the task. These can be directly used in Google Colab. If you want to use them locally, follow the steps to install graph_tool from [here](https://graph-tool.skewed.de/static/doc/index.html) and remember not to run the first box in most of the notebooks which installs graph_tool (Feel free to try if you're feeling adventurous though!).
- **Text_Data** - Has a single file, the arXiv API data saved by us.

The main dependency is graph_tool. Other libraries used are networkx, matplotlib, numpy, seaborn, tabulate, collections, datetime, time, dateutil, random, pickle, bs4, requests, pandas, and google.colab.