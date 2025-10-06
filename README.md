# Fencing Score Predictor
This project served as an exercise to improve my skills in developing neural networks.

## Data
Raw data is obtained through the FIE 'General Ranks' sheet which stores the points scored by each athlete in each competition. The general ranks for the 2025/2026 season can be found [here](https://fie.org/athletes/general-ranks/?category=S&ag=-1&weapon=F&gender=M&event=I&season=2026&country=).

The data is transformed into a single Panda dataframe, and additional features such as the athlete's FIE ID and date of birth are scraped from the FIE website, as seen in the `data.ipynb` notebook.
