
 import pandas as pd

def load_data(filename):
    try:
        df = pd.read_csv(filename)
        return df
    except FileNotFoundError:
        print(f"File '{filename}' not found.")
        return None

def main():
    # Replace 'doctor_visits.csv' with your file name if it's different
    file_path = "doctor_visits.csv"

    # Load the data from CSV
    df = load_data(file_path)
    if df is None:
        return

    # Basic statistics
    num_visits = len(df)
    num_patients = df['Patient_ID'].nunique()
    most_common_symptom = df['Symptoms'].mode().iloc[0]
    most_common_diagnosis = df['Diagnosis'].mode().iloc[0]

    # Medication analysis
    medication_counts = df['Medication'].value_counts()
    most_common_medication = medication_counts.index[0]
    most_prescribed_medication = medication_counts.idxmax()

    # Print results
    print("Doctor Visit Analysis Report:")
    print(f"Total visits: {num_visits}")
    print(f"Total patients: {num_patients}")
    print(f"Most common symptom: {most_common_symptom}")
    print(f"Most common diagnosis: {most_common_diagnosis}")
    print(f"Most common medication: {most_common_medication}")
    print(f"Most prescribed medication: {most_prescribed_medication}")

if __name__ == "__main__":
    main()
