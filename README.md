# Causal-Intervention-on-VL-Models
This is the repository for the Implementation of Causal Mediation Analysis on the Vision-Language Transformer BLIP, focussed on the Visual Question Answering task of colour identification in images and questions sourced from the COCO-QA Dataset from the paper "Exploring Models and Data for Image Question Answering"

BLIPforVQA or Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation Transformer is a sequential encoder and decoder model, which takes as input an image and a question, each of which is sent into an Image Encoder and an Image Grounded Question Encoder. 

The Image Grounded Question Encoder also obtains the image embedding output from the Image Encoder as an input, following which it generates Question Embeddings. These Question Embeddings are sent into the Answer Decoder alongside a BOS(Beginning-Of-String) ID --> [Decode] which allows it to decode the tensors into open-ended Answers
<p align="center">
<img width="366" alt="Screenshot 2023-07-06 at 4 14 33 PM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/73601c35-549e-4a48-a42b-3dca966aa288" >
</p>
<p align="center">
<i>BlipforVisualQuestionAnswering Architecture</i>
</p>


Causal Tracing by our methodology involves introducing noise to the Image Embeddings, and creating a batch of 2 image embeddings being input into the Question Encoder - one being uncorrupted and the other being corrupted. Following this, we hook the outputs of different layers inside the encoder and patch the uncorrupted states to the corrupted states. 





