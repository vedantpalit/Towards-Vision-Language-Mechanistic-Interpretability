# Towards-Vision-Language-Mechanistic-Interpretability

This is the repository for the Implementation of Causal Mediation Analysis on the Vision-Language Transformer BLIP, focussed on the Visual Question Answering task of colour identification in images and questions sourced from the COCO-QA Dataset from the paper "Exploring Models and Data for Image Question Answering"

BLIPforVQA or Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation Transformer is a sequential encoder and decoder model, which takes as input an image and a question, each of which is sent into an Image Encoder and an Image Grounded Question Encoder. 

The Image Grounded Question Encoder also obtains the image embedding output from the Image Encoder as an input, following which it generates Question Embeddings. These Question Embeddings are sent into the Answer Decoder alongside a BOS(Beginning-Of-String) ID --> [Decode] which allows it to decode the tensors into open-ended Answers
<p align="center">
<img width="400" alt="Screenshot 2023-07-06 at 4 14 33 PM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/73601c35-549e-4a48-a42b-3dca966aa288" >
</p>
<p align="center">
<i>Blip for VQA Architecture</i>
</p>


Causal Tracing by our methodology involves introducing noise to the Image Embeddings, and creating a batch of 2 image embeddings being input into the Question Encoder - one being uncorrupted and the other being corrupted. Following this, we hook the outputs of different layers inside the encoder and patch the uncorrupted states to the corrupted states.

<p align='center'>
<img width="756" alt="Screenshot 2023-07-23 at 11 21 43 PM" src="https://github.com/Vedantpalit/Towards-Vision-Language-Mechanistic-Interpretability/assets/102275067/d7212438-91c6-49ed-ab1f-95d89bd373f9">

</p>
<p align='center'>
<i>Visualization of Patching of States for Interpretability</i>


</p>


The following are the results of causal tracing on a couple of samples alongside the corresponding images:\
**Example 1:**
<p align='center'>
<img width='400' src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/ed5afb35-c228-4ae8-81f2-f5f5d1c57ff0">
</p>
<p align='center'>
<i>COCO-QA ID:000000220218 Image and Causal Trace Heatmap</i>
</p>
<p align='center'>
<img width="561" alt="Screenshot 2023-08-22 at 1 43 58 PM" src="https://github.com/vedantpalit/Towards-Vision-Language-Mechanistic-Interpretability/assets/102275067/d17a7b15-9229-4f76-9247-2968be891e3a">
</p>


**Example 2:**
<p align='center'>
<img width='400' src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/f84fde27-6aef-4171-b353-2451e1cecb57">
</p>
<p align='center'>
<i>COCO-QA ID:000000458864 Image and Causal Trace Heatmap</i>
</p>
<p align='center'>
<img width="561" alt="Screenshot 2023-08-22 at 1 44 07 PM" src="https://github.com/vedantpalit/Towards-Vision-Language-Mechanistic-Interpretability/assets/102275067/080b0c99-e6ce-4ac5-b67d-fd2d1d72ebe9">
</p>














