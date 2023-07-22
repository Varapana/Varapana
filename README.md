
 
   


```python
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
data = pd.read_csv('doctor_visits.csv')  # Replace 'doctor_visits.csv' with the path to your dataset

# Preview the data
print(data.head())

# Perform basic analysis
# Example 1: Count the number of doctor visits by gender
gender_counts = data['Gender'].value_counts()
print(gender_counts)

# Example 2: Visualize the distribution of age
plt.hist(data['Age'], bins=10, edgecolor='black')
plt.xlabel('Age')
plt.ylabel('Count')
plt.title('Distribution of Age')
plt.show()

# Example 3: Analyze the frequency of different diagnoses
diagnosis_counts = data['Diagnosis'].value_counts().head(10)
print(diagnosis_counts)

# Example 4: Calculate the average visit duration
avg_duration = data['Duration'].mean()
print(avg_duration)
```

 
