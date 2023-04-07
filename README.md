


 Project description:

    We plan to create an AI model that can date music to a decade or specific year.
    Can music be linked to a specific time period? If so, which songs fit into the period when they were created, and which are more difficult to place?
    Can musical trends from a time period be read as patterns by an AI model?
    These are the questions we want to answer. We will likely use a neural network to train a model, but we are open to exploring what answers we could get from other types of models.
    Apart from handling matrices and tensors, I don't know how close the algorithms we use in training our models will be.
    Services that want to identify and categorize music, or recommend music to users, should be interested. Alternatively, the model could be built into an app for people who, for fun or knowledge, want to know when a song was created.

 

 Theory:

    We have chosen to use different models of sequential neural networks. We have chosen to use Tensorflow as a tool to build these neural networks. The models we chose to use are:
    
    - Recurrent neural network: with 4 layers.
    - Convolutional neural network: with 13 layers.
    - Multilayer: with 5 layers, where the first layer is a Flatten layer.
    - Multilayer overfitting: with 8 layers, where the first layer is a Flatten layer, and layers 3, 5, and 7 are Dropout layers.
    We found that the Multilayer overfitting model worked best, and graphs/statistics on this can be seen in the models_history folder.
    Problems and solutions that arose during the project:
    Initially, we had put all the songs and all the years in the same dataset. This became very difficult for the neural network to make sense of. So the solution to this was that we had to rebuild the dataset into several datasets. So the structure of the datasets became, one dataset with all genres, and then each genre has a dataset where the year is the outcome. So our app consists of several trained models.
     
 The structure of how our app runs:

    1. It predicts genres on the song it receives.
    2. Then, depending on which genre it predicts, it goes to the trained genre model and predicts which year the song is from.

# Running

 Preparing data:

    1. conversion_utils.py : If you want to convert mp3 song to wav.
    2. first_preparation_of_dataset.py : Changes name and add a number to every song.
    3. prepare_dataset.py : Mapping and pick out mfcc values to a json dataset.

 Model training:
    
    1. We have four different neural networks you can train with, multilayer_model_overfitting.py is the one that works best and is also the one on which the app runs.
       You can find all neural networks in neural_networks/

    2. Run multilayer_model_overfitting.py on all files in data_json/

 App:

    Run the app by running main.py

    The app is built with the help of 10 different models, the first model predict what genre it is on the song. 
    Then depending on what genre it predict it is. 
    Then it goes on to predict what year the song is from, in the specific genre.



