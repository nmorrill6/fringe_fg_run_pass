# Predicting Pass or Run in Fringe Field Goal Range

American Football is the most popular sport in the USA. Millions of children and youth around the country participate in organized football each year. College football is hugely popular both to play and watch, with the NCAA reporting an annual revenue of $1.3 billion for the 2022-2023 football season. Professional football, the NFL, is also extremely popular, with reported annual revenue for 2024 being over $23 billion dollars. Fans, players, and teams all want to win, and by analyzing the behavior of offenses in the NFL, we can help defense prepare to stop their opponents and increase their chance of winning. 

We analyze team behavior and try to predict whether an offense will pass or run the ball in what we have determined to be "fringe field goal range". This part of the field is 40-55 yards away from the defensive team's endzone. We ask the question: are some teams more predictable in this part of the field than others? What makes these teams more predictable than others? After an extensive analysis, we provide a proven framework for answering these questions in this repo. Given more weeks of data from the NFL, we believe this framework would be even more effective at answering these two questions.

## Video Overview
https://youtu.be/Fr_kMVNXA3Q?si=t4xiFe-ga-ADpNqr

## Main analysis
The main analysis and framework is found in `notebooks/main_notebook.ipynb`

## Research Questions
1. Are some teams more predictable than others in terms of if they will pass or run the ball in fringe field goal range?
2. If the answer to the above question is yes, what signals do they give that defenses can use to predict run or pass?

## Data
The data used for this analysis is NFL proprietary data released for the 2025 Big Data Bowl competition used for educational purposes as per their license specifications. It consists of the data collected from the first 9 weeks of the 2024-2025 NFL season across all 32 teams. This data is no longer available for download, but here is the link where you can find more info about the dataset: https://www.kaggle.com/competitions/nfl-big-data-bowl-2025/data.

The fields used for this prediction problem are:
- `quarter`: (numeric) which quarter of of the game this play took place in
- `yardsToGo`: (numeric) how many yards to the first down marker
- `possesionTeam`: (string) 3 letter abbreviation for the offensive team for this play
- `defensiveTeam`: (string) 3 letter abbreviation for the defensive team for this play
- `yards_to_endzone`: (numeric) absolute number of yards from current line of scrimmage to the defensive team's endzone
- `seconds_remaining_in_quarter`: (numeric) number of seconds left in the quarter
- `preSnapOffTeamWinProbability`: (numeric) calculated from the NFL provided metrics `preSnapHomeTeamWinProbability`, `preSnapVisitorTeamWinProbability`, and `possessionTeam`
- `offenseFormation`: (string) formation used by possession team
- `receiverAlignment`: (string) enumerated as 0x0, 1x0, 1x1, 2x0, 2x1, 2x2, 3x0, 3x1, 3x2
- `playClockAtSnap`: (numeric) what the play clock value was at time of snap
- `is_pass`: (binary) indicator for if the play was a pass play or a run play by the offense


## Getting started
You would have to get data similar to the data found above in order to run the code in these notebooks. If you do, here is how to get started.
1. Create and activate a conda environment
```
conda create -n pass_or_run python=3.12
conda activate pass_or_run
```
2. Install packages in requirements.txt
```
pip install -r requirements.txt
```
3. Select pass_or_run kernel for `notebooks/main_notebook.ipynb` and run

## File Structure
```
fringe_fg_run_pass/
├─ README.md
├─ .gitignore
├─ checkpoints/
│  ├─ checkpoint_1.ipynb
   └─ checkpoint_2.ipynb
└─ notebooks/
   └─ main_notebook.ipynb
```

## Results Summary
As seen below, some teams are more predictable than others! By analyzing their data more closely (see `notebooks/main_notebook.ipynb`) we can see why they are more predictable compared to other teams, and defenses can use this information to better defend against them. We were able to show with these results and those found in `notebooks/main_notebook.ipynb` that this is a robust, scalable framework for analyzing the predictability of any NFL team passing or running the ball withing the fringe field goal range (40-55 yards from opponent's endzone). However, 9 weeks of data is not a lot for a problem as complex as this. In order to get the best predictions possible we would need to collect more data for analysis.
<img width="1813" height="774" alt="image" src="https://github.com/user-attachments/assets/76ad58d9-7a4b-47b5-892c-baf4256af855" />
<img width="1359" height="937" alt="image" src="https://github.com/user-attachments/assets/62d57811-9d4f-428c-aaed-c8aeda6d24bc" />
