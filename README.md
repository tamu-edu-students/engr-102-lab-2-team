# ENGR 102 Lab Topic 2 (team)

## Activities
This lab consists of three team activities. Please submit the following files to Canvas and Gradescope. Create the file for Sequential Algorithm and Giving Instructions using a word processing program such as Word or Google Docs, then **save that as a PDF for submission**. Please put the names of all team members that contributed at the top of each document. For Linear Interpolation, be sure to include the team version of the header information at the top of your code. This is a team assignment, but everyone must submit your files. You may discuss the problems with other teams, but your submitted work must be unique. Check out the [Frequently Asked Questions](#frequently-asked-questions) below. 

1. [Sequential Algorithm](#sequential-algorithm) submit to Canvas
2. [Giving Instructions](#giving-instructions) submit to Canvas
3. [Linear Interpolation](#linear-interpolation) submit to Gradescope

## Sequential Algorithm
Description

## Giving Instructions
Description

## Linear Interpolation
The purpose of this activity is to practice writing simple programs that require multiple variables, and to ensure you understand the idea of interpolation. One of the activities in the topic 2 individual lab will build on this program. ***Please refer to Canvas for the posted material on Linear Interpolation.***

You are an engineer at NASA monitoring the International Space Station (ISS) as it orbits the Earth at a constant rate of speed. You want to be able to predict where the ISS is above the Earth at any point in time. To do this, you take a measurement of how far around the Earth the ISS has traveled at two points in time. Assume that NASA has very precise instruments for determining position. You note the time of the first position, and a short while later (before the ISS has completed one revolution), you take a second measurement for how far the ISS has traveled, again noting the time.

Now, it’s your job to reconstruct the position of the ISS at any time between the first and second measurements. Since you assume the ISS is moving at a constant speed, this calculation can be found via linear interpolation. As a team, determine what variables you will need to use, and what formula(s) you will need to perform this calculation. *You should use variables for all of the values that could change.*

**Part 1**<br/>
The first measurement was taken at time t=10 minutes, and the second was taken 45 minutes **later**. At the first measurement, the ISS was 2,029 kilometers past Houston, TX. At the second measurement, the ISS was 23,029 kilometers past Houston.

-	Write a program that determines, for any time between 10 and 55 minutes, where the ISS will be (in terms of kilometers past Houston). The time at which to evaluate should be a variable in your program. The program should print both the time and the position at that time to the screen, with a line describing what is being output (**see example output below**). You should test your program at various times and make sure the results seem reasonable.
-	For your final program that you submit, output the position at a time of 25 minutes. (Next week, we will see how you can read in numbers from a user, but for now, just assume it is a fixed number of minutes.)

**Questions to think about**: What happens if you enter t=0 minutes as the time of interest? What is output as the position at that time? How do you interpret this result? Should the position at t=0 minutes be at Houston? **Suggestion**: Hand draw a sketch of position versus time and plot the two known observations. Now, predict from the sketch what the calculated position will be for t=0 minutes or for t=1500 minutes.

**Part 2**<br/>
Now, let’s make this a bit more interesting. The ISS orbits in a circle with **radius 6,745 kilometers**. Use the same observed data as before: at 10 minutes, the ISS is 2,029 kilometers past Houston, and at 55 minutes, the ISS is 23,029 kilometers past Houston. Assume its speed is constant.  

When a time is specified, we want to report the *distance past Houston*, not the total distance traveled. So, every time the ISS passes Houston, its “distance” past Houston gets reset to zero (0). So, if you go far into the future, say at a time of 5 hours (300 minutes), simple linear interpolation will not produce the result we want. You’ll need to modify your code to report distances correctly regardless of the time.

Here are a few hints for Part 2:
-	If we use the same code from above and enter a time of 300 minutes (5 hours), we calculate a distance greater than the orbit’s circumference. (Estimate that calculated distance from your plot.)
-	However, we want to report a position of the ISS between 0 kilometers and the numerical value of the orbit’s circumference expressed in kilometers.
-	We could do this using a series of subtractions. We could perform successive subtractions of the circumference from the total position until the result was between 0 kilometers and the numerical value of circumference in kilometers. That would represent the position with respect to Houston. 
-	If we were clever, we could also use “modulo division” in Python. (Remember from Lecture 1?)
-	**Questions to think about**: Is this linear “extrapolation”? If so, why are we are we using linear extrapolation despite all the warnings not to use it? Is there ever a case when using linear extrapolation is acceptable?
-	**Another Question to think about**: Will the code for Part 2 output the correct answer for time (t) of 25 minutes as was used in Part 1?

Please put your code for Parts 1 and 2 into one file named `linear_interpolation.py` for submission to Gradescope. Include the team header at the top of your code (see Canvas for the header information). Use a comment to clearly label the two parts.

Example output:
```
Part 1:
For t = 25 minutes, the position p = 9029.0 kilometers
Part 2:
For t = 300 minutes, the position p = 10222.078642554414 kilometers
```

## Frequently Asked Questions
1. **Does everyone on the team need to submit the files?** Yes! Everyone needs to submit all of the (same) assignment files for credit. Why? Because linking students in groups in Gradescope and Canvas is a huge pain for us.

2. **Do I have to submit a pdf? Can I submit docx or something else?** No! Pdfs render quite nicely in Canvas. Other formats do not. Please make grading easier on us!

3. **How detailed should my instructions be?** Include enough detail that someone can follow along without needing extra materials. Some things that are obvious to you may not be obvious to others!
  
4. **What's the difference between linear interpolation and extrapolation?** Linear interpolation calculates a value between two known points. Extrapolation attempts to calculate a value outside two points. Linear interpolation is a common calculation in engineering. Extrapolation is generally avoided (when possible) because it is less accurate. Why is it less accurate? Because calculus.

5. **Linear interpolation part 2 how do I do the calculation without a loop/if statement?** There's this really cool math operator in python: `%`. Don't remember what that is? Go back and review lecture 1!

6. **Linear interpolation part 2 the last two digits in my answer is different from the example!** Did you use your calculator to calculate the circumference of the orbit? Did you hard code that number into your code? Don't do that! Python is your calculator in this class, so use code to calculate the value and store it in a variable.

Have a question you don't see here? Email your instructor!

Based upon Dr. Keyser’s Original<br/>
Revised Summer 2025 SNR
