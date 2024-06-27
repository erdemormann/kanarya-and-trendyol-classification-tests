# Kanarya and Trendyol Classification Tests

I have tested the Kanarya and Trendyol models for the classification problem on the Turkish tweet hate speech detection dataset.

### [Kanarya-750m](https://huggingface.co/asafaya/kanarya-750m)

**basic-kanarya.ipynb** file contains the code and results for testing the trained and untrained Kanarya model on detecting hate speech in tweets from the X platform. 

Due to hardware limitations, I was barely able to train the model. However, for comprehensive training, you can achieve much better results by increasing the values of parameters such as batch_size and epoch, and by tuning hyperparameters like learning_rate.

Results of Untrained Kanarya-750m with a classification header added:

| f1 score (macro) | f1 score (micro)| f1 score (weighted)
| ------------- | ------------- | ------------- |  
 | 0.42 | 0.43 | 0.44  |

**prompt_kanarya.ipynb** file contains experiments using the Kanarya model's text generation capabilities without modifying the model or adding a classification header. This file includes the code for classification using the prompt approach, optimized with Bitsandbytes and LoRA techniques. However, the experiment did not perform classification as intended and instead continued generating text based on the learned data, resulting in a failed attempt.


### [Trendyol-LLM-7b-chat-dpo-v1.0](https://huggingface.co/Trendyol/Trendyol-LLM-7b-chat-dpo-v1.0)

**prompt_trendyol_v2.ipynb** file includes a study that optimizes and trains the Trendyol model using the prompt approach with Bitsandbytes and LoRA techniques. The work encompasses both testing of the untrained model and code for its training. Due to hardware limitations, despite optimization techniques, I couldn't train the model.

Additionally, the study includes code and results that involve testing the model's behavior with different prompt trials for the untrained model. 

Here is the result of it:

| prompt | f1 score (macro) | f1 score (micro)| f1 score (weighted)
| ------------- | ------------- | ------------- | ------------- | 
| "Metni negatif veya pozitif olarak sınıflandır."   | 0.41| 0.67  | 0.55  |
| "Bir metin nefret içeriyorsa veya tehdit, kişisel saldırı, iftira veya istismar gibi metinsel nefret içeriyorsa nefret içerikli olarak sınıflandırılır. Bir metin, olayları bildiriyorsa veya başkalarının görüşlerini nefret içermeyen bir şekilde objektif olarak bildiriyorsa nefret içermeyen olarak kabul edilir."  | 0.36  | 0.40  | 0.42  |

**Note:** You can run all code files directly on Kaggle or Colab platforms with a T4 GPU.
