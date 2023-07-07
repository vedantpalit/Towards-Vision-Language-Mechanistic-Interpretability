# Causal-Intervention-on-VL-Models
This is the repository for the Implementation of Causal Mediation Analysis on the Vision-Language Transformer BLIP, focussed on the Visual Question Answering task of colour identification in images and questions sourced from the COCO-QA Dataset from the paper "Exploring Models and Data for Image Question Answering"

BLIPforVQA or Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation Transformer is a sequential encoder and decoder model, which takes as input an image and a question, each of which is sent into an Image Encoder and an Image Grounded Question Encoder. 

The Image Grounded Question Encoder also obtains the image embedding output from the Image Encoder as an input, following which it generates Question Embeddings. These Question Embeddings are sent into the Answer Decoder alongside a BOS(Beginning-Of-String) ID --> [Decode] which allows it to decode the tensors into open-ended Answers
<p align="center">
<img width="400" alt="Screenshot 2023-07-06 at 4 14 33 PM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/73601c35-549e-4a48-a42b-3dca966aa288" >
</p>
<p align="center">
<i>BlipforVisualQuestionAnswering Architecture</i>
</p>


Causal Tracing by our methodology involves introducing noise to the Image Embeddings, and creating a batch of 2 image embeddings being input into the Question Encoder - one being uncorrupted and the other being corrupted. Following this, we hook the outputs of different layers inside the encoder and patch the uncorrupted states to the corrupted states.

<p align='center'>
<img width='640' src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/736286cf-0d1b-4ff4-9c9a-b92149c05c1c">
</p>
<p align='center'>
<i>Visualization of Corruption of Image Embedding for Causal Tracing</i>


</p>


The following are the results of causal tracing on a couple of samples alongside the corresponding images:\
**Example 1:**
<p align='center'>
<img width='400' src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/ed5afb35-c228-4ae8-81f2-f5f5d1c57ff0">
</p>
<p align='center'>
<i>COCO-QA ID:000000220218 Image and Causal Trace</i>
</p>
<p align='center'>
<img width="360" alt="Screenshot 2023-07-07 at 10 44 22 AM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/8ed766d8-cc2a-4821-b157-13b7cefa9de0"><img width="360" alt="Screenshot 2023-07-07 at 10 44 30 AM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/b028a471-716b-4452-bf97-24f7e32a669d">
</p>


**Example 2:**
<p align='center'>
<img width='400' src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/45cf1f7c-79a4-4f3e-9d5f-38c57d927fe0">
</p>
<p align='center'>
<i>COCO-QA ID:000000458864 Image and Causal Trace</i>
</p>
<p align='center'>
<img width="360" alt="Screenshot 2023-07-07 at 10 36 45 AM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/4bf00db5-3c3f-4d97-987b-54b873e74c69"><img width="360" alt="Screenshot 2023-07-07 at 12 49 45 PM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/47bed1b7-aea0-47cb-9da3-061adf865f06">
</p>













