# Week 10 Labs

Ok, its been awhile but i'm back at it. I did 25% of the course over the summer, now fall semester is over (pretty much) and i'm going to try to get this course done by febuary (ideally over winter break). I've learned a lot since the last time I was here

Highlights of the semester: 

- got an internship, where I did web dev stuff 15 hours a week
- started and led an event for CS+Social Good (weekly talks)
- Joined a Marine Robotics competition  lab, on the Perception team (helped automate the data collection process in different worlds, learned some python, am going to be doing cool Computer Vision stuff next semester. hence this course finally coming in handy!)



Now, on to what I did today 

# Week 10 labs

## Part 2: Maximum Likelihood

- this took more time than part 3 did, but still wasn't too bad. The formulas from the lecture were extremely helpful. It basically boiled down to creating a list of likelihoods from possible valeus they gave us, finding the max, and indexing back to the original value they gave.
- a lot of it was me getting used to matlab syntax again (sigh)

## part 3a: Linear regression model

- they passed in a feature matrix and ground truth labels. This step made the weights of a learned model. 
- this was just using matlabs equation solver (trivial, just a backslash basically)

## part 3b: prediction

- this brought back memories of statistics (y hat)
- here we basically transposed the weights vector and we made the predictions through element wise matrix multiplication 
- it took me some time to get the dimensions right of the problem after the matrix multiplication. It wanted 1 column and I was giving 7. But I sumed along rows and it fixed that up. 

## part 3c: Error estimation

- this part was cool (and pretty easy). 
- just implementing a formula for the error ((actual-expected)^2)/2
- our average error score was 6.8003 

## part 1? Bayes Rule and Marginalization 

So I spent a lot of time on this part before giving up. The discussion forums and my tests supported the idea that the autograder was broken so i didn't waste time here. The last posts were from an instructor 8 months ago saying they would look into it….. I also covered this topic in the statistics course I am currently taking (Math 3670) and it felt a little tedious to redo (got 100 on the midterm for that class anyway, so i'm pretty confident in stats). Might come back to this though. 



In general I'd say today was a success: i'm getting back into it! This took my progress from 25 to 26% overall in the course. I plan to study for the midterm (weeks 1-6) over the break and take that, so that should bring me closer to completion. After completion I intend to continue as time permits, but with a pretty heavy course load lets see how that goes. 