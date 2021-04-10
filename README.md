# Reducing-Commercial-Aviation-Fatalitites:-

Reducing Commercial Aviation Fatalities is a Kaggle competition held in 2019. Aviation Fatalities/accidents cause deaths of passengers, aircrew, and complete vehicle damage, etc. Most flight-related fatalities stem from a loss of “airplane state awareness.” That is ineffective attention management on the part of pilots who may be distracted, sleepy, or in other dangerous cognitive states.

# Dataset Overview -

Dataset consists of real physiological data from 9 crews(18 pilots) who were subjected to various distracting events. There are 3 files provided by Kaggle, viz. Train, test, sample submission all in CSV types.
Training set consists of a set of controlled experiments collected in a non-flight environment, outside of a flight simulator.
Test set (abbreviated LOFT = Line Oriented Flight Training) consists of a full flight (take off, flight, and landing) in a flight simulator.

Pilots experienced distractions intended to induce/produce one of the following 3 cognitive states:

Channelized attention:- this is an engaged state of mind where the pilot excludes other tasks and only remains focused on one task.
Diverted attention:- it can be understood as multitasking when the pilot is involved in handling multiple things at a time and cannot properly focus which leads to a lack of decision making.
Startle/Surprise:- this can be understood when sudden unexpected events happen during flight, events can be anything and dangerous by which the pilot gets surprised and starts focusing on handling troubling events.

# Features Overview -
ID - (test set and sample submission file only) A unique identifier for a crew + time combination.
crew - a unique id for a pair of pilots. There are 9 crews/pilots in the data.
experiment - One of CA, DA, SS, or LOFT(only present in the test set).
time - seconds into the experiment
seat - is the pilot in the left (0) or right (1) seat
event - The state of the pilot at the given time. This a class label.

Physological features:
EEG - Electroencephalography(EEG) is an electrophysiological monitoring method to record the electrical activity of the brain.

ECG - An electrocardiogram is a test that measures the heart's electrical activity. It’s also known as an ECG or EKG. Every heartbeat is triggered by an electrical signal that starts at the top of the heart and travels to the bottom. The sensor had a resolution/bit of .012215 µV and a range of -100mV to +100mV. The data are provided in microvolts.

respiration(r) - Respiration, a measure of the rise and fall of the chest. The sensor had a resolution/bit of .2384186 µV and a range of -2.0V to +2.0V. The data are provided in microvolts.

GSR - Galvanic Skin Response, a measure of electrodermal activity. The sensor had a resolution/bit of .2384186 µV and a range of -2.0V to +2.0V. The data are provided in microvolts.

# Performance Metric -
This Kaggle problem statement is a 4 class classification problem and evaluation to be done using Multi-Class Log Loss between the predicted probabilities and the observed target. Following are 4 Class Labels to be classified: A = baseline B = SS C = CA D = DA

Why Multiclass Log-Loss as evaluation metrics?

In our case, we are solving classification problem in which Machine Learning model have to predict each class among 4 classes.
In this problem getting misclassified prediction cannot be tolerated as per Business perspective, using Multi-Class log loss will penalize even small deviations from actual output which is very helpful.
when data is highly imbalanced ROC curve is not a good choice to go with.
