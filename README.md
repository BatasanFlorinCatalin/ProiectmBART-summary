# ProiectmBART-summary
This project takes the audio from a .wav file and generates a summary of the speech in the audio file, to do this it uses Whisper to transcribe the 
speech into text which is then feed to mBART-50/LLaMA to generate the summary( only the LLaMA model generates comprehensive summaries ).

Instructions:

Select the desired model; you can choose mBART-50 or Llama 3.1 8-B Instruct.
Download the training and testing datasets: "test_data", "train_data".
Download the desired audio file.
Open the .ipynb file in Google Colab.
Upload the files to the "Files" section on the left side of the screen using the "Upload" button.
For both models, insert the audio file path into the third line of code in the second cell in Colab.
Then, run the code up to the Text Summary section and display the WER score.
Run each cell one by one until you reach the Training section. Here, you can modify the training parameters, and then continue with training the model. At the end of each epoch, the model is saved in the "mbart-rezumate-ro" folder.

!For mBART:
  To load the desired model resulting from the training, copy the model path from the "mbart-rezumate-ro" folder into the "nume_model_hf" variable and run the cell.
  Run the code up to the Rezultate (Results) section. To summarize a text, create a variable containing the text to be summarized and call the summarize() function, which takes a string as a parameter. The returned text is saved in a variable, e.g., "summary".
  To view the text summary, use the command print(f'summary : {summary}') (if the summary was saved under this name).
  To calculate the score resulting from the evaluation metrics, use the following functions:
  
metrica_sacrebleu.compute(predictions=[], references=[])
rezultat_rouge = metrica_rouge.compute(predictions=[], references=[])
rezultat_ter = ter_metric.compute(predictions=[summary3], references=[rezumat_summary3])

  To visualize the obtained scores, use the following functions:
plot_bleu_score()
plot_rouge_score()

!For LLaMA:
  Run each cell up to the Training section. Here, you can modify the training parameters, after which you continue with the training.
  In the Upload section, proceed the same way as with mBART-50: choose the desired model from the "rezultate_llama_8b" folder and save its path in the cale_adaptor_lora variable.
  To calculate and display the results, run all cells up to the TesteazaSiPloteazaMaster function. This function calculates and displays the 3 scores from each metric; it takes the original text and a reference summary as parameters.
