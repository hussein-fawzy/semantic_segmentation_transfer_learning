This is an implementation of semantic segmentation transfer learning.
<br><br>
The model implemented here is based on the model developed in the paper "*The devil is in the labels: Semantic segmentation from sentences*".
<br>
The authors claim that their method, while operating in zero-shot setting, achieves results comparable to those of supervised learning; and it was possible by replacing the class labels with embeddings generated from sentences. Furthermore, fine-tuning the model to a given semantic segmentation dataset, should further improve the performance of the model.
<br>
The target is to adapt the original model to a new dataset; in this case, the *CMP Facade Database*
<br><br>
**Development Steps:**
*   Copy required functions from the original paper code to the Google Colab document (and update as required)
*   Create an iterator for the new dataset to suit the implementation
*   Allow the model to freeze the encoder while updating gradients for the head
*   Give meaningful explanation to the *CMP Facade Database* labels and use them to build embeddings. The explanations are obtained from [*merriam-webster*](https://www.merriam-webster.com/) while the embeddings are build with the  CLIP-ViT model (Same as the paper)
*    Integrate [*Weights & Biases*](https://wandb.ai/) to track experiment results. This step is done to show the relation between hyper-parameters and model performance
*    Fine-tune the model using the *CMP Facade Database*
*    Evaluate the performance of the model using the Mean IoU metric
<br>

**How To Use:**
Copy the Google Colab document in ssiw_transfer_learning_cmp_implementation to your Google Drive then open it, adjust the required training parameters and run the script.
<br>
A fine-tuned model already exists in the models directory.
<br>
Predictions from different trained models are available in the predictions directory.
<br>

**Notes:**
*    The *CMP Facade Database* consists of two datasets, base ane extended. The base dataset is used for training while the extended extended dataset is used for testing
*    The GPU memory, on Google Colab, may sometimes be filled, that is why garbage collection is called on multiple points in the code

**Links:**
*    ["The devil is in the labels: Semantic segmentation from sentences" Paper](https://arxiv.org/abs/2202.02002)
*    [Original Code Github Repository](https://github.com/irfanICMLL/SSIW/tree/master)
*    [CMP Facade Database](https://cmp.felk.cvut.cz/~tylecr1/facade/)
*    A link is provided in the Results section below for the results report