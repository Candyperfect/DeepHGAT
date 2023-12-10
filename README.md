# Predicting Protein Functions based on Heterogeneous Graph Attention Technique
<p align="center">
    <br>
    <img src="./fig/DeepHGAT.png?raw=true" width="800" height="381"/>
    <br>
</p>
In bioinformatics, protein function prediction stands as a fundamental area of research and plays a crucial role in addressing various biological challenges, such as the identification of potential targets for drug discovery and the elucidation of disease mechanisms. However, known functional annotation databases usually provide positive experimental annotations that proteins carry out a given function, and rarely record negative experimental annotations that proteins do not carry out a given function. Therefore, existing computational methods based on deep learning models focus on these positive annotations for prediction and ignore these scarce but informative negative annotations, leading to an underestimation of precision. To address this issue, we introduce a deep learning method that utilizes a heterogeneous graph attention technique. The method first constructs a heterogeneous graph that covers the protein-protein interaction network, ontology structure, and positive and negative annotation information. Then, it learns embedding representations of proteins and ontology terms by using the heterogeneous graph attention technique. Finally, it leverages these learned representations to reconstruct the positive protein-term associations and score unobserved functional annotations. It can enhance the predictive performance by incorporating these known limited negative annotations into the constructed heterogeneous graph. Experimental results on three species (i.e., Human, Mouse, and Arabidopsis) demonstrate that our method can achieve better performance in predicting new protein annotations than state-of-the-art methods. 

**1.Environment Settings**
* python == 3.8  
* Pytorch == 1.12.1
* Numpy == 1.23.5 
* SciPy == 1.9.3 
* dgl == 0.9.1.post1 
* networkx == 2.8.4
* scikit-learn == 1.2.0 
* fair-esm ==0.4.0

**2.Usage**

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
