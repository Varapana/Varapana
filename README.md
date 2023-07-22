# Sample Doctor Visit Analysis Code

# Data for doctor visits
doctor_visits = [
    {"patient_id": 1, "date": "2021-05-10", "duration": 30, "symptoms":["fever", "cough"], "diagnosis": "common cold"},
    {"patient_id": 2, "date": "2021-05-11", "duration": 60, "symptoms":["headache", "fatigue"], "diagnosis": "migraine"},
    {"patient_id": 3, "date": "2021-05-12", "duration": 45, "symptoms":["sore throat", "body ache"], "diagnosis": "tonsillitis"},
    {"patient_id": 4, "date": "2021-05-12", "duration": 20, "symptoms":["rash", "itching"], "diagnosis": "allergic reaction"}
]

# Analyzing doctor visits
num_visits = len(doctor_visits)
average_duration = sum(visit["duration"] for visit in doctor_visits) / num_visits
common_symptoms = []
for visit in doctor_visits:
    common_symptoms.extend(visit["symptoms"])
most_common_symptom = max(set(common_symptoms), key=common_symptoms.count)

# Output
print("Doctor Visit Analysis:")
print("----------------------")
print("Number of visits: {}".format(num_visits))
print("Average visit duration: {} minutes".format(average_duration))
print("Most common symptom: {}".format(most_common_symptom))
