### Authors: [Nicola Cassetta](https://github.com/NicolaCST), [Andrea Di Trani](https://github.com/AndreaDiTrani) 

# Decepticon: Frank Wolfe and attention against ViT

We used the Frank-Wolfe optimization algorithm - and its variants - to generate adversarial examples, in both white and black box scenario, as well as in the untargeted and targeted case. We also propose a novel attack based on the combination of the FW and the attention maps generated by the ViT, in order to speed up the black-box attack.

## Results
In the white-box scenario, our AsR (Attack success Rate) is much higher than the results reported in 'On the Robustness of Vision Transformers to
Adversarial Examples' by Kaleel Mahmood, Rigeln Mahmood, Marten Van Dijk', even using a much lower distortion (ϵ = 0.01 instead of ϵ = 0.062)

![Screenshot](/res/res_white.png)


### Frank-Wolfe
The FW is one of the oldest methods for constrained convex optimization and, recently, it has seen an impressive revival due to the proof of some nice proprieties even in a non-convex scenario. Here we analyzie the behaviour of:

- Standard Frank-Wolfe
- Frank-Wolfe Pairwise
- Frank-Wolfe Fully-Corrective


### Decepticon: FW Black-box and Attention
In order to speed up the gradient estimation step, we merged the different attention heatmaps of the ViT into a single map, then we used a threshold in order to
keep only the most relevant parts. At this point we used the heatmap as a sequence of coordinates, and used these coordinates as a ’mask’ in order to avoid the sampling of the full image.

![Screenshot](/res/attention_ex.PNG)


### Example Images
#### FW white-box untarget
![Screenshot](/res/white_ex.png)


#### FW white-box target
Target class: "White wolf"

![Screenshot](/res/white_target.png)


#### FW Black-box + Attention
![Screenshot](/res/black_attention_ex.png)
