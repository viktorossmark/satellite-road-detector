# Satellite road detector
Notebooks illustrating how to find road networks and represent them as graphs from satellite imagery. For the road segmentation we are using a U-net with ResNet-blocks (skip connections) DNN architecture. The segmented imagery is then represented as graphs, which will allow us to efficiently find optimal paths within the road networks.

## U-net with ResNet-blocks architecture
The code for constructing and training the network below can be found in the notebook -> segmentation.ipynb.

<img width="814" alt="resnet_unet_scheme" src="https://user-images.githubusercontent.com/64202661/119328986-037b0c00-bc85-11eb-94d6-a5d5486ff8f7.png">


## Sample predictions
Model trained on 918 satellite images taken over Las Vegas (with corresponding ground truth masks). The data can be found and downloaded at https://spacenet.ai/spacenet-roads-dataset/.

<img width="916" alt="vegas_sample_pred" src="https://user-images.githubusercontent.com/64202661/119326621-5ef7ca80-bc82-11eb-9cfc-31ce46a00900.png">

## Image-to-graph vizualizations
The code for representing a predicted mask (output from DNN model) as a graph can found in the notebook -> image2graph.ipynb. 
### Step 1: Post-process
<img width="1010" alt="post_process_stp" src="https://user-images.githubusercontent.com/64202661/119329646-bba8b480-bc85-11eb-8401-a692cd2090d5.png">

### Step 2: Skeletonize
<img width="846" alt="skeleton_ex" src="https://user-images.githubusercontent.com/64202661/119329908-f6125180-bc85-11eb-8062-1faecb49c75e.png">

### Step 3: Build graph
<img width="678" alt="mask_graph_ex" src="https://user-images.githubusercontent.com/64202661/119329951-0296aa00-bc86-11eb-926c-a879fd1e0e3e.png">

## Optimal routing using Dijkstra
The implementation of Dijkstas shortest path algorithm can also be found in -> image2graph.ipynb. The evaluation of how effective we can find optimal routes (compared to the ground truth optimal paths) can be found in -> evaluate.ipynb. The metric we use is denoted as the Optimal Top-to-Bottom Similarity score and is defined according to the equation below. In the example below, the OTBS-score is 0.98. 

<img width="860" alt="opt_path_eval" src="https://user-images.githubusercontent.com/64202661/119330185-396cc000-bc86-11eb-9dc2-d1c6fe37d808.png">
<img width="1085" alt="otbs2" src="https://user-images.githubusercontent.com/64202661/119343157-5b6e3e80-bc96-11eb-9701-341ac842e6cb.png">
