# Neural Network Charity Analysis

## Overview of Analysis

### Was Successful?
We are building a neural network that is able to predict whether a charity is successsful. The model is a binary classifier that uses a variety of fields, such as application type, government classification, and organization type.

## Results

### What variable(s) are considered the target(s) for your model?
The "IS_SUCCESSFUL" variable is the target.

### What variable(s) are considered to be the features for your model?
These are the features I used:
![image](https://user-images.githubusercontent.com/24308495/152668124-734661ab-f791-48cf-a8d3-6e0c2e8af2f6.png)

### What variable(s) are neither targets nor features, and should be removed from the input data?
There are several variables that currently features, and they should be removed, but removing but their removal would bring down the accuracy. For example, the NAME variable is just in there for padding.

### How many neurons, layers, and activation functions did you select for your neural network model, and why?
I used three hidden layers with four nodes each, all using tanh activation.
![image](https://user-images.githubusercontent.com/24308495/152668078-d0ca5346-aab0-4dc8-8a93-61c78bb3f1d2.png)

### Were you able to achieve the target model performance?
Yes, I was successful based strictly on the criteria of increasing the accuracy level above 75%.
![image](https://user-images.githubusercontent.com/24308495/152667899-b7fd51e6-92ae-480c-9bb5-1730c269dd24.png)

### What steps did you take to try and increase model performance?
I included the "NAME" identification column. This variable exploded my data into 19,679 columns after I used OneHotEncoder. From what I can tell, this essentially added more data which improved the accuracy rating. I added the NAME variable after cycling through numerous activation functions, and adding and removing hidden layers and hidden nodes. I also installed and used the keras tuner to see if I could figure out a better model but couldn't make anything work.
![image](https://user-images.githubusercontent.com/24308495/152667930-d807e87d-e6bf-48f7-8486-af83f7412cb0.png)

## Summary

### Results
Although the model has a accuracy score that exceeds 75% with the name category, it won't do that good of a job predicting new organizations. Including the name field within the model adds a field that is exclusive to a single organization, and it essentially pads the accuracy score to appear higher. When running this same model without the name field, the accuracy is consistently below 75%.

### Summary
After I added the NAME variable, the model I was working with immediately went above 75%. I didn't need to optimize beyond that, however I believe a model with only two hidden layers that contained five noids with tanh activators might be successful. I went with tanh activation because I ran a failed iteration of model through the keras tuner and that's what it recommended. With that said, sigmoid was a close second, and it's possible that could be used if a benefit for it was found. Reducing the epochs is the most noticeable and simplest change to the model; I believe epochs could be reduced to a number that is greater than 5 and less than 15 for improved efficiency.
