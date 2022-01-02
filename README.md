# Workflow_Prioritisation
Medical workflow prioritisation - emergency setting

_In this exercise we are given the following:_

A list of images that have come in through the ED in order of patient arrival
Probabilities of 'brain bleed' for each image, as determined by one of your deep learning algorithms
Probabilities of 'aortic dissection' for each image, as determined by one of your deep learning algorithms.

_We need to do the following:_

Calculate the amount of time it will take before each image is read by the radiologist, given the patient arrival queue, assuming each image takes 6 minutes to read
Implement a heuristic that uses the probabilities returned by your two algorithms to re-order the priority read list, assuming that brain bleeds and aortic dissections are equally urgent
Calculate the time delta for each image between the initial and the re-ordered priority reads.

_Sotulion:_
`max_prob` column is created which takes the max of either `Brain_bleed_probability` or `Aortic_dissectin_probability`.

And re-order the dataframe according to this `max_prob`. So the images with larger probability are put at the top of the queue.

Next, `time_to_read_prioritized` column is created that is simply values incremented by 6 minutes per row. This is the new reading time based on the re-ordered queue.

Finally, `time_delta` column is `time_to_read` minus `time_to_read_prioritized` so that you could get a sense of how much time is saved from the original order.


