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
<img width='640' src="!https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/42a20731-11a9-45cf-a914-1be08f4c6e27">
</p>
<p align='center'>
<i>Visualization of Corruption of Image Embedding for Causal Tracing</i>

</p>


The following are the results of causal tracing on a couple of samples alongside the corresponding images:\
**Example 1:**
<p align='center'>
<img width='400' src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/12552ee8-ad05-4c3d-b474-9846a249d9b4">
</p>
<p align='center'>
<i>COCO-QA ID:000000220218 Image and Causal Trace</i>
</p>
<p align='center'>
<img width="360" alt="Screenshot 2023-07-07 at 10 44 22 AM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/abfefad7-6eb5-456c-8402-f81bcdc74db2"><img width="360" alt="Screenshot 2023-07-07 at 10 44 30 AM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/b29da4a0-7d8f-42bd-bdd3-87c5b7d0194c">
</p>

**Example 2:**
<p align='center'>
<img width='400' src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/45cf1f7c-79a4-4f3e-9d5f-38c57d927fe0">
</p>
<p align='center'>
<i>COCO-QA ID:000000458864 Image and Causal Trace</i>
</p>
<p align='center'>
<img width="360" alt="Screenshot 2023-07-07 at 10 36 45 AM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/704319a0-9737-461a-a94f-c3ed6a16e1f9"><img width="360" alt="Screenshot 2023-07-07 at 10 40 53 AM" src="https://github.com/Vedantpalit/Causal-Intervention-on-VL-Models/assets/102275067/4f8874eb-8ba8-4231-9447-b15f448f9519">
</p>











