# Fencing Score Predictor
This project served as an exercise to improve my skills in developing neural networks.

## Data
Raw data is obtained through the FIE 'General Ranks' sheet which stores the points scored by each athlete in each competition. The general ranks for the 2025/2026 season can be found [here](https://fie.org/athletes/general-ranks/?category=S&ag=-1&weapon=F&gender=M&event=I&season=2026&country=).

The data is transformed into a single Panda dataframe, and additional features such as the athlete's FIE ID and date of birth are scraped from the FIE website, as seen in the `data.ipynb` notebook. However, this code has now been **deprecated**, due API changes. The dataset could still be found [here](https://www.kaggle.com/datasets/foillee/fencing-points).

## Model
Results in competitve sports are largely stochastic, to make predictions, we therefore require a more complex predictor than simple linear regression. To model this complexity, I first used RNNs then LSTMs to get around the vanishing/exploding gradients as seen commonly in RNNs. To make better predictions, I incoporated features such as age, and fencer nationality into the dataset. By utilising a GPU with PyTorch, the whole notebook only takes minutes to fully execute. I've experimented with a variety of hyperparameter configurations and feel satisfied with the result.

## Predictions
The objective of this work was to forecast the performance of athletes, we use the number of points scored in a competition as a proxy for the athlete's overall performance and can forecast an athlete's performance for any amount of time. Below I showcase some predictions my model has made and compare with with actual data.

<img width="574" height="476" alt="Foconi_eval" src="https://github.com/user-attachments/assets/4113771f-1c33-4ee2-be48-0ab1bfafae7c" />
This seems like a sensible prediction, Foconi, whilst an exceptional fencer at his age, is nearing the end of his fencing career and will most likely not be able to compete with fencers reaching their peaks.

<img width="562" height="476" alt="Itkin_eval" src="https://github.com/user-attachments/assets/11d5f44b-f118-4425-98e0-6a8d7710c085" />
Another sensible forecast here, Nick Itkin is still quite young and could reach is peak soon.

<img width="574" height="476" alt="Meinhardt_eval" src="https://github.com/user-attachments/assets/a382ead9-54e7-47ee-986b-e466a7b8ca68" />
The model makes a pessimistic forecast for Meinhardt, most likely due to his age (he is 35 in the year 2025).





