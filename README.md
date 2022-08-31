
# Tractor Service Time Prediction

This data contains info related to mahendra Tractor service.
the target was to find the time taken by the service,
based on NLP and service chain of different problems and its own times.




## Features

* 'Project Type'
* 'Severity of Problem'
* 'Warrantable/Non Warrantable'
* 'Type of ORC'
* 'Failure Date'
* 'Problem Definition (Step-1)',
* 'Observations (Step-2)'
* 'System'
* 'Sub System'
* 'Under Analysis (Step-3)'
* 'Solution Identification & Release (Step-4)'
* 'Solution Validation & ORC Closure (Step-5)
* 'Solution Implementation (Step-6)'
* 'Conclusion and Tracking (Step 7)'
* 'ORC Current Status'
* 'Date of ORC Creation'
* 'Date to reach at Step 2'
* 'Date to reach at Step 3'
* 'Date to reach at Step 4'
* 'Date to reach at Step 5'
* 'Date to reach at Step 6'
* 'Date to reach at Step 7'
* 'Time to Solution Release (days)'
* 'Time to Close the ORC (days)'
* 'Remarks'



## Problems
 Finding the target variable itself was a problem.
 the target variable was numerical and did not have normal distribution.
 to make a proper and clear target we have classified it and made
 the problem to a classification problem.

 Target: 'Time to Close the ORC (days)'
 * Before Classification 

![before cleaning](https://user-images.githubusercontent.com/98254459/187660359-23e2af4d-6ba2-45d8-b1a5-acfe97074b01.png)

 * After Classification

        The classes are basically the Days.
![after classification](https://user-images.githubusercontent.com/98254459/187660652-21226b05-fa5b-4796-97e7-2c4664a143be.png)

 we also had 5 rows that had days going above 100.
 Since it is very less data we cleared the rows as they are faulty.

 *'Failure Date'
    
    this column was full of dates trying to find
    how this feature could contribute we have ploted and found the 
    below result.

![FailureDate](https://user-images.githubusercontent.com/98254459/187660942-1865ee3e-31e8-4d12-9fa9-73eef00cb488.png)
so for different classes they actully show the peak months.
1,4,10,12.
but if we see they dont clearly contribute a lot in defineing
between the 4 classes, there are lot of miss clarity.
so we have made a tough decition to drop this feature.

* NLP 
The biggest problem was there were lot of NLP info.
Most of the data was related to nlp.

* System
![System](https://user-images.githubusercontent.com/98254459/187661210-c16b8aa2-a00e-4c79-89f8-6fde234bb414.png)

this also has data classified into all the time types.
but if we see the count of the data it is 5 rows or 2 rows mostly.
this huge spread will contribute only when we have a large amount of data
inour hands. here we choose to drop as the pattern cannot be found 
it will only over fit. this was again a problematic decition.

* Sub System.

    it had 75 unique values out of 149 rows.
    clear lead to overfit it was. we have droped the column.
    

 
## Word Cloud
    The data is a 50-50 contribution of NLP and Numeric data
    overall its a classification problem.
    Since NLP has a lot of contribution Word cloud seemed
    to fit the requirement and also we have only taken
    step one into consideration as there were no null values
    and had a lot of meaning.

![WordCloud](https://user-images.githubusercontent.com/98254459/187661423-70239c0b-c2cd-4e03-9c20-226336f8f1ed.png)

TDF vector has not been used yet.
so we are seeing observe and tractor to be main words yet.



## Model Performance
As we know our models are going to be classification models.
we have used 5 models namely(logistic regression, KNN, DT, Random Forest and also XG-Boost)

our biggest problem was the models had very less amount of data to train and learn.
the scores was like wise.
* logistic Regression - 0.81
* KNN - 0.40 (overfitted with 1 nearneighbour)
* DT - 0.83 (12 was the best depth)
* RF - 0.60 (8 was the best depth)
* XG-Boost - 0.868 (learning rate was 0.16)

considering all the results we have also ploted confusion matrix.

![XGBoost](https://user-images.githubusercontent.com/98254459/187661654-1fb202a1-e816-42e8-bd76-2af0436db8f8.png)

with very less data to learn it has actully done better.
the result is anyway a non overfitted one.
 
## Conclusion
This is a project to analyse the NLP and Time serise data we have also calculated and predicted how long this might take for take for a partiuclar service problem to be solved.
Here the data was very less and the outcome is also based on that. the positive fact is we have got a score of 0.87. 