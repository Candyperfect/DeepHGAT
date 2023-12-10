# README
"[Predicting Protein Functions based on Heterogeneous Graph Attention Technique]"

# Environment Settings 
* python == 3.8  
* Pytorch == 1.12.1
* Numpy == 1.23.5 
* SciPy == 1.9.3 
* dgl == 0.9.1.post1 
* networkx == 2.8.4
* scikit-learn == 1.2.0 
* fair-esm ==0.4.0

# Usage 
Please first **unzip** the data folders and then use. 
````
humancc/
├─link.dat: Yeast protein sequence.    
├─lint.dat.test: taxonomic similarity and direct acyclic graph of GO term.   
└─node.dat: Yeast protein functional annotations
````
Enter the folder path：./methods/
````
python run_new.py --dataset [humancc/mousecc/arathcc/humanmf/mousemf/arathmf/humanbp/mousebp/arathbp]
````
