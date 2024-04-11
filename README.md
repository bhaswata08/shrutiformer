# Video Demo
[![Demo for ISL based Sign Language Detection](https://img.youtube.com/vi/WsnubMzE8yM/0.jpg)](https://youtu.be/hR-aP7o53iQ)


# Problem Statement

## Addressing the Communication Gap between Deaf and Non-Deaf Communities in South Asia, Particularly India

**Overview:**

South Asia, including India, is home to a significant portion of the global deaf population. Despite estimates suggesting a high number of individuals affected by hearing loss, accessibility and sign language resources are limited in India. The National Association of the Deaf puts the number at 18 million, while other sources indicate it could be as high as 63 million.

The lack of accessibility and communication tools poses challenges for education and employment opportunities for the deaf community. Efforts to establish Indian Sign Language as an official language are ongoing, and the need for innovative solutions to bridge the communication gap persists.

# Dataset Details:

Dataset has been sourced from AI4Bharat (source: https://zenodo.org/record/4010759).

The INCLUDE dataset has 4292 videos The videos used for training are mentioned in train.csv (3475), while that used for testing is mentioned in test.csv (817 files). Each video is a recording of 1 ISL sign, signed by deaf students from St. Louis School for the Deaf, Adyar, Chennai.
<br/>
For our Prototype, we have included 8 
categories with 79 videos in Train split, 14 videos in test split and 11 videos in validation split. 

The given categories are assessed.
- Beautiful
- Blind
- Deaf
- Happy
- Loud
- Quiet
- sad
- Ugly


# Model Details:

For real time Sign Language Detection, We've tested two distinct models: an LSTM-based model and a Transformer-based model.
<br/>
The LSTM model leverages keypoints extracted from Mediapipe for poses, which are then fed into the recurrent neural network (RNN) for evaluation.

On the other hand, the Transformer model is trained after experimentation involving a range of transformations and hyperparameter tuning to optimize its performance.

These two approaches offer unique pathways for analyzing and interpreting input data, catering to different requirements and scenarios within our application.
<br/>

The VideoMAE model was proposed in VideoMAE: Masked Autoencoders are Data-Efficient Learners for Self-Supervised Video Pre-Training by Zhan Tong, Yibing Song, Jue Wang, Limin Wang. VideoMAE extends masked auto encoders (MAE) to video, claiming state-of-the-art performance on several video classification benchmarks.

Several techniques such as qLORA, peft, and head and backbone fine-tuning and only head fine-tuning was tried and Ultimately, only fine-tuning the head and backbone of the model was found out to be successful, in our case.

Model was fine-tuned in several stages: \n
- RUN 1: Fine-tuned using linear scheduler with constant decay for initial training. Run 1 was not as successful as we hoped hence forth run 2 was initialized.
- RUN 2: A hyperparameter grid search was conducted for the given run for finding the optimal hyperparams. 
- RUN 3: A final run was initialized which was successful.
  <br/> <br/> <br/>
<b>Find the Training Reports here:</b> https://github.com/pranjalkar99/shruti-drishti/issues/9

## Model Checkpoints:
https://huggingface.co/bhaswata08/MAEFORMER

# Solution

## Leveraging Deep Learning for Sign Language Translation

**Approach:**

Our proposed solution involves using deep learning models to facilitate communication:

1. **Sign Language to Text:**
   - Implement a custom Transformer-based Multi-Headed Attention Encoder using Google's Tensorflow Mediapipe for converting sign language videos into text.
   - Address challenges related to dynamic signs similarity by utilizing keypoint data generated by Google's Tensorflow Mediapipe.

2. **Text to Sign Language:**
   - Reproduce the methodology outlined in the paper [link to paper], specifically tailored for Indian Sign Language.
   - Utilize a Generative Adversarial Network (GAN) model to convert textual information into structural keypoints and further generate sign language videos.

**Use Cases:**

1. **Workplace and Educational Inclusion:**
   - Deploy the Sign Language Generation system in offices and educational institutions to facilitate seamless communication with the deaf and mute community.
   - Empower individuals with hearing impairments by providing them with equal opportunities for education and employment.

2. **Content Accessibility:**
   - Enable news channels and content creators to expand their user base by making their content accessible and inclusive.
   - Offer services to embed sign language video layouts for content, fostering a more inclusive society and promoting equal participation.

# Action Plans

1. **Pose-to-Text Implementation:**
   - Develop and implement a Pose-to-Text model based on the paper [link to paper] for the Indian Sign Language dataset.
   - Utilize Gemini/GPT-4 as the decoder stage for text-to-gloss conversion.

2. **Custom Transformer Model Evaluation:**
   - Assess the effectiveness of our custom Transformer model on the Sign Language Dataset, focusing on accuracy and adaptability to dynamic signs.

3. **Multilingual App Development:**
   - Create a user-friendly multilingual app serving as an interface for our Sign Language Translation services.
   - Ensure the app facilitates easy interaction and adoption by both deaf and non-deaf users.

# Progress So Far

- [x] Basic Deep Learning-based LSTM model for sign language recognition (Done)
- [x] Custom multi-headed attention-based encoder for sign language recognition for dynamic signs (Done)
- [x] Testing on the whole Indian dataset for our attention model (In Progress)
- [ ] Implementing the pose-to-text and the implementation of the paper (In Progress)
- [ ] Build multilingual app (To Do)

## Proposed Workflow (credits to the Open Source Paper)
![image](https://github.com/pranjalkar99/shruti-drishti/assets/74347116/4636a003-09f4-4953-92ad-c3df4b9fea1e)

## Results:

[![image](https://github.com/pranjalkar99/shruti-drishti/assets/74347116/3541813b-52c2-4c10-a7ac-88096aac62b4)](https://www.canva.com/design/DAF_IfblIbM/Hm_cvyUw6vNEf8-RXg68fg/edit?utm_content=DAF_IfblIbM&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

<br/>
![Uploading image.png…]()
(https://www.canva.com/design/DAF_IfblIbM/Hm_cvyUw6vNEf8-RXg68fg/edit?utm_content=DAF_IfblIbM&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)



## Other Links:

Demo video: [Click](https://www.youtube.com/watch?v=hR-aP7o53iQ)
Other Presentation slides: [Click](https://www.canva.com/design/DAF_IfblIbM/Hm_cvyUw6vNEf8-RXg68fg/edit?utm_content=DAF_IfblIbM&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
Hasgeek Presentation slides:  [Click](https://www.canva.com/design/DAGABnVhHqw/d2T8fLDof94PabPlWoKHEg/edit?utm_content=DAGABnVhHqw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
Any other document you want us to read: 
 ISL History and its need: [Click](https://islrtc.nic.in/history-0#:~:text=Indian%20Sign%20Language%20(ISL)%20is,material%20that%20incorporates%20sign%20language.) 
Project Roadmap Github View: [Click](https://github.com/users/pranjalkar99/projects/2/views/2)



 
#### Project Contributors:
**Pranjal Kar** (https://github.com/pranjalkar99/)
**Bhaswata Choudhury** (https://github.com/bhaswata08)
**Samunder Singh** (https://github.com/samthakur587)



(we thank the authors of the paper https://aclanthology.org/2023.at4ssl-1.3.pdf for the architectural flow, and workflow, our open source project is aimed at research for Indian usecases)
**Note:**
The development and research is under progress.
