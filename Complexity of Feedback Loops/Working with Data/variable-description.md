## Full description of data set variables. Please also read the associated paper for more details.

intervals  
shape : (nTrials, 2)  
2 column array giving each trials start (i.e. beginning of quiescent period) and stop (i.e. end of iti) times of trials in universal seconds
 
included  
shape : (nTrials)  
boolean suggesting which trials to include in analysis, chosen at experimenter discretion, e.g. by excluding the block of incorrect trials at the end of the session when the mouse has stopped
 
repNum  
shape : (nTrials)  
the repetition number of the trial, i.e. how many trials have been repeated on this side (counting from 1)
 
goCue_times  
shape : (nTrials)  
Time of go cues in choiceworld - in absolute seconds from session start, rather than relative to trial onset. NOTE: this is the time the sound is actually played.
 
goCueTrigger_times  
shape : (nTrials)  
Time of go cues in choiceworld - in absolute seconds from session start, rather than relative to trial onset. NOTE: this is the time the trigger command is sent.
 
response_times  
shape : (nTrials)  
Time (in absolute seconds from session start) when a response was recorded (end of the closed loop state in bpod)
 
choice  
shape : (nTrials)  
which choice was made in choiceworld: -1 (turn CCW), +1 (turn CW), or 0 (nogo)
 
stimOn_times  
shape : (nTrials)  
Times of visual stimulus onset in absolute seconds.
 
stimOnTrigger_times  
shape : (nTrials)  
Times of visual stimulus onset trigger command, from session start in seconds
 
contrastLeft  
shape : (nTrials)  
contrast of left-side stimulus (0...1) nan if trial is on other side
 
contrastRight  
shape : (nTrials)  
contrast of right-side stimulus (0...1) nan if trial is on other side
 
feedback_times  
shape : (nTrials)  
Time of feedback delivery (reward or not) in choiceworld - in absolute seconds, rather than relative to trial onset.
 
feedbackType  
shape : (nTrials)  
Whether feedback is positive or negative in choiceworld (-1 for negative, +1 for positive)  
 
rewardVolume  
shape : (nTrials)  
volume of reward given each trial in µl  
 
itiDuration  
shape : (nTrials)  
Intertrial interval duration for each trial, from response time to end of trial (end of trial is beginning of quiescence period) this includes the feedback delivery and the 1or 2 seconds delay and the 0.5 sec iti at the end of each trial.
 
deadTime  
shape : (nTrials)  
time between state machine trial end and restart for every trial trial_length + iti_duration
   
probabilityLeft  
shape : (nTrials)  
Probability that the stimulus will be on the left hand side for the current block. The probability of right is 1-probabilityLeft  
