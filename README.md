# Satellite road detector
Notebooks describing how to find road networks and represent them as graphs from satellite imagery. For road segmentation we are using a Res-Unet DNN architecture. The segmented imagery is then represented as graphs, which will allow us to find optimal paths within the road networks.

## U-net with ResNet-blocks architecture

<img width="814" alt="resnet_unet_scheme" src="https://user-images.githubusercontent.com/64202661/119328986-037b0c00-bc85-11eb-94d6-a5d5486ff8f7.png">


## Sample predictions
Model trained on satellite imagery taken over Las Vegas. The data can be found and downloaded at https://spacenet.ai/spacenet-roads-dataset/

<img width="916" alt="vegas_sample_pred" src="https://user-images.githubusercontent.com/64202661/119326621-5ef7ca80-bc82-11eb-9cfc-31ce46a00900.png">

## Image-to-graph vizualizations
### Step 1: Post-process
<img width="1010" alt="post_process_stp" src="https://user-images.githubusercontent.com/64202661/119329646-bba8b480-bc85-11eb-8401-a692cd2090d5.png">

### Step 2: Skeletonize
<img width="846" alt="skeleton_ex" src="https://user-images.githubusercontent.com/64202661/119329908-f6125180-bc85-11eb-8062-1faecb49c75e.png">

### Step 3: Build graph
<img width="678" alt="mask_graph_ex" src="https://user-images.githubusercontent.com/64202661/119329951-0296aa00-bc86-11eb-926c-a879fd1e0e3e.png">

## Optimal routing using Dijkstra
<img width="860" alt="opt_path_eval" src="https://user-images.githubusercontent.com/64202661/119330185-396cc000-bc86-11eb-9dc2-d1c6fe37d808.png">

