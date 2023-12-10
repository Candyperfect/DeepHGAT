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
This data folder contains nine datasets on three species (Human, Mouse and Arabidopsis) and three branches of ontology (CC, MF and BP). Please first **unzip** the data folders and then use. For example,
````
humancc/
├─link.dat: edge information of the constructed heterogeneous graph for training (format: node rank->node rank->edge type->score)   
├─lint.dat.test: annotation information between proteins and GO terms for testing  (format: node rank->node rank->edge type->score)  
└─node.dat: features of proteins and GO terms (format: node rank->node name->node type->feature, the sequence features obtained by the ESM_1b and the GO features based on the Ohe-hot encoding)
````
Enter the folder path：./methods/model/
````
python run_new.py --dataset [humancc/mousecc/arathcc/humanmf/mousemf/arathmf/humanbp/mousebp/arathbp]
````
The results are stored as a .txt file and output in the current folder, (format: protein node rank->term node rank->edge type->score).
