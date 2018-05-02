How to Demo Our Project

Clone our Git Repository (on Linux): https://github.com/DrFicus/CS460_Final_Project 

There are two folders in our final project demo code. 
The first folder, FinalProjectResearch_Control, contains data that we collected with very few variables. For example, we ensured that the CPU fan was always running, we stopped recording immediately after encryption or decryption completed, and we used the same file each time.
The second folder, FinalProjectResearch_Experimental, contains data that we collected with more variables. We didn’t worry about the CPU fan being on or off, we randomized recording time before and after encryption or decryption, and we used different files each time.

Change your directory to: 
FinalProjectResearch_Control/FinalProjectResearch/audioClassifications

The audioClassifications directory contains several files and folders: createClassifierModel, testClassifierModel, trainingData, and sampleData. 
The trainingData directory has three sub-directories: EncryptionData, DecryptionData, and RegularProcessingData. The EncryptionData sub-directory contains audio recordings from when we encrypted files, the DecryptionData sub-directory contains audio recordings from when we decrypted files, and the RegularProcessingData sub-directory contains audio recordings from when we just had Google Chrome running. 
These three sub-directories were used to train the audio classifier. We created a small Python script to train the audio classifier and this script is called createClassifierModel. To train the model, run the following command via the command-line: 

$ ./createClassifierModel trainingData

We also have a directory called sampleData which contains five audio recordings of either decryption or encryption. These were recorded separately from the trainingData audio files. To test if an audio file is encrypting, decrypting, or just performing normal processing, run the following command via the command-line, replacing ‘X’ with a number between 1 and 5:

$ ./testClassifierModel sampleData/newRecordX.wav

The output of the command will either specify which label was chosen for the audio file or it will just say ‘Sound classification not certain’. We also took the liberty to print out the actual percentages that the model generated. While testing the model we sometimes found that the audio file would not get classified, but it would evaluate one label higher than others. Looking at those evaluations we confirmed that the software would correctly classify the audio if the probability was set to a lower percentage. We set the probability at 0.5, which means that any label with a probability greater than or equal to 0.5 will get chosen as the classified label for the audio file.

Repeat the same exact process to run and test the demo for the Experimental data in the FinalProjectResearch_Experimental folder. This data includes relevant audio files of encryption and decryption, but with random durations and random start and end times as mentioned before in step 1.
