## Dataset access
IBL Data can be downloaded from Figshare: [link](https://figshare.com/articles/A_standardized_and_reproducible_method_to_measure_decision-making_in_mice_Data/11636748)

The data is contained in NumPy `.npy` files organized in a hierarchy of subfolders following this structure: `/{lab}/Subjects/{subject}/{date}/{number}/alf/`

You can use the ONE interface to load the data in Python. The script `one_example.py` shows an example of searching and retrieving the data locally. You need Python 3.6+ and ibllib 1.4.7+. ibllib depends on a number of packages, including NumPy, SciPy, pandas, matplotlib. At the moment we recommend that you install ibllib in a fresh Python environment, as follows: `virtualenv ibl`, `source ibl/bin/activate`, `pip install ibllib`.

To launch the script, go into the data directory named `ibl-behavior-data-Dec2019`, and type `python one_example.py`. This script will only work if you launch this command from within that directory, as the ONE loader takes the current directory as data source by default.

## Dataset types description

_ibl_trials.intervals
shape : (nTrials, 2)
2 column array giving each trials start (i.e. beginning of quiescent period) and stop (i.e. end of iti) times of trials in universal seconds

_ibl_trials.included
shape : (nTrials)
boolean suggesting which trials to include in analysis, chosen at experimenter discretion, e.g. by excluding the block of incorrect trials at the end of the session when the mouse has stopped

_ibl_trials.repNum
shape : (nTrials)
the repetition number of the trial, i.e. how many trials have been repeated on this side (counting from 1)

_ibl_trials.goCue_times
shape : (nTrials)
Time of go cues in choiceworld - in absolute seconds from session start, rather than relative to trial onset. NOTE: this is the time the sound is actually played.

_ibl_trials.goCueTrigger_times
shape : (nTrials)
Time of go cues in choiceworld - in absolute seconds from session start, rather than relative to trial onset. NOTE: this is the time the trigger command is sent.

_ibl_trials.response_times
shape : (nTrials)
Time (in absolute seconds from session start) when a response was recorded (end of the closed loop state in bpod)

_ibl_trials.choice
shape : (nTrials)
which choice was made in choiceworld: -1 (turn CCW), +1 (turn CW), or 0 (nogo)

_ibl_trials.stimOn_times
shape : (nTrials)
Times of visual stimulus onset in absolute seconds.

_ibl_trials.stimOnTrigger_times
shape : (nTrials)
Times of visual stimulus onset trigger command, from session start in seconds

_ibl_trials.contrastLeft
shape : (nTrials)
contrast of left-side stimulus (0...1) nan if trial is on other side

_ibl_trials.contrastRight
shape : (nTrials)
contrast of right-side stimulus (0...1) nan if trial is on other side

_ibl_trials.feedback_times
shape : (nTrials)
Time of feedback delivery (reward or not) in choiceworld - in absolute seconds, rather than relative to trial onset.

_ibl_trials.feedbackType
shape : (nTrials)
Whether feedback is positive or negative in choiceworld (-1 for negative, +1 for positive)

_ibl_trials.rewardVolume
shape : (nTrials)
volume of reward given each trial in µl

_ibl_trials.itiDuration
shape : (nTrials)
Intertrial interval duration for each trial, from response time to end of trial (end of trial is beginning of quiescence period) this includes the feedback delivery and the 1or 2 seconds delay and the 0.5 sec iti at the end of each trial.

_ibl_trials.deadTime
shape : (nTrials)
time between state machine trial end and restart for every trial trial_length + iti_duration

_ibl_trials.probabilityLeft
shape : (nTrials)
Probability that the stimulus will be on the left hand side for the current block. The probability of right is 1 minus this
