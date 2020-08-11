# You okay?
## Analyzing employee absenteeism with Python, SQL, and Tableau

Using data science and machine learning to who figure out who is more likely to click on an ad.

## Summary:

Extracting information from company data to predict whether an employees abscense based on the the illness as well as a number of contributing factors.

The approach taken to solve this problem proceeded as follows:

- Feature engineering
    - Exploratory data analysis
    - Engineered datetime features to bucket weekdays and months
    - Scaled and normalized numerical features
    - Engineered sickness reasons into separate, more generalized buckets
- Machine Learning
    - Used Logistic regression achieve:
    - **Accuracy of 78%**
    - Highlighted feature importance using coefficients
- SQL integration
    - Initialized a MYSQL database with processed, predicted data for further analysis
- Data Visualization
    - Illustrated findings using Tableau(https://public.tableau.com/profile/alexander.bennett#!/vizhome/Employee_Absenteeism/AgeVsProbability?publish=yes)

    - **Check out the Tableau link!**


## Findings:

-  Average probability for certain ages to have a prolonged absence.
    - A 28 year old (youngest age available) is 59% more likely to be excessively absent (more than three hours) if they are away for being sick. Conventional wisdom would suggest that they younger the person, the less likely they are to be down for the count. Interesting find.

- Reasons:
    1 - Illness/Disease
    2 - Pregnancy/Birth related
    3 - Poison/Other
    4 - Routine/Appointment

    - Exploratory visualizations show that if a person is supposed to be absent, and it's for reason 1, the likelihood that they are away for an extended period of time (3 or more hours) is above 50%. This qualitative takeaway is supported by the logical separation made to bin all serious diseases in this reason. If someone is away for this coded reason, they will be most likely be excessively absent


    - Reason 4 shows the opposite conclusion from group 1. The data shows that someone who is scheduled to be unavailable is more than 50% likely to be away for less than three hours. This logic checks out with the idea that someone leaves work for an appointment, and comes back because it is not as serious as reason 1.


- Transportation Expenses and Children

    - Before filtering by # of children, there is a slight positive correlation between travel expense (proxy for distance from the office) and the probability that they are absent for longer than 3 hours for a planned health absence. This makes sense. The father away you are, the less likely it is that you'll be able to available around a planned medical absence.

    - People with 0 children don't exhibit a high probablity for excessive absence, they also don't have high transportation expenses

    - The distribution of people with 1 or 2 children signalled that it wasn't necessarily the # of children that filtered out a more glaring probability. In general, the majority of data is found with people who spend less than $240 a month on transportation.

    