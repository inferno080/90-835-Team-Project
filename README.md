# 90-835-Team-Project

## User Journey

1. Run the Python notebook till you reach the last cell. At the last cell, you will be greeted with a UI, where you will have the option to upload patient data.
2. The expected format of the data is a JSON Array. Upload a .json file on the UI.
3. If your upload was successful, you should be redirected to a new page where you can genrate discharge letters
4. Select the patient whose summary you want to generate from the dropdown.
5. Add a custom prompt, where you can specify additional notes. eg. Make it very easy to understand for a six year old
6. Generate the letter and download your pdf.

## Images



### Sample Data To Upload

```[
    {
        "patient_id": "123456",
        "patient_demographics": {
          "name": "John Doe",
          "age": 70,
          "gender": "Male",
          "admission_date": "2024-02-10",
          "discharge_date": "2024-02-14"
        },
        "diagnoses": [
          {
            "date": "2024-02-10",
            "diagnosis_code": "J18.1",
            "description": "Lobar pneumonia, unspecified organism"
          }
        ],
        "drg": {
          "code": "193",
          "description": "Simple pneumonia and pleurisy with MCC"
        },
        "encounters": [
          {
            "date": "2024-02-10",
            "type": "Admission",
            "reason": "Cough, shortness of breath, hemoptysis, fever"
          },
          {
            "date": "2024-02-14",
            "type": "Discharge"
          }
        ],
        "flowsheets": [
          {
            "date": "2024-02-10",
            "time": "08:00",
            "temperature": "38.5°C",
            "heart_rate": "90 bpm",
            "blood_pressure": "130/85 mmHg",
            "respiratory_rate": "20 breaths/min",
            "oxygen_saturation": "92%"
          },
          {
            "date": "2024-02-11",
            "time": "08:00",
            "temperature": "37.8°C",
            "heart_rate": "85 bpm",
            "blood_pressure": "125/80 mmHg",
            "respiratory_rate": "18 breaths/min",
            "oxygen_saturation": "94%"
          },
          {
            "date": "2024-02-12",
            "time": "08:00",
            "temperature": "37°C",
            "heart_rate": "80 bpm",
            "blood_pressure": "120/75 mmHg",
            "respiratory_rate": "16 breaths/min",
            "oxygen_saturation": "96%"
          },
          {
            "date": "2024-02-13",
            "time": "08:00",
            "temperature": "36.5°C",
            "heart_rate": "78 bpm",
            "blood_pressure": "118/74 mmHg",
            "respiratory_rate": "14 breaths/min",
            "oxygen_saturation": "98%"
          }
        ],
        "imaging": [
          {
            "date": "2024-02-10",
            "type": "Chest X-Ray",
            "findings": "Consolidation in left lower lobe"
          }
        ],
        "labs": [
          {
            "date": "2024-02-10",
            "tests": [
              {
                "name": "CRP",
                "result": "60 mg/L"
              },
              {
                "name": "WBC",
                "result": "12 x10^9/L"
              },
              {
                "name": "Hemoglobin",
                "result": "13.5 g/dL"
              },
              {
                "name": "Platelets",
                "result": "250 x10^9/L"
              }
            ]
          },
          {
            "date": "2024-02-11",
            "tests": [
              {
                "name": "CRP",
                "result": "50 mg/L"
              },
              {
                "name": "WBC",
                "result": "11 x10^9/L"
              },
              {
                "name": "Hemoglobin",
                "result": "13.3 g/dL"
              },
              {
                "name": "Platelets",
                "result": "245 x10^9/L"
              }
            ]
          },
          {
            "date": "2024-02-12",
            "tests": [
              {
                "name": "CRP",
                "result": "35 mg/L"
              },
              {
                "name": "WBC",
                "result": "9 x10^9/L"
              },
              {
                "name": "Hemoglobin",
                "result": "13.1 g/dL"
              },
              {
                "name": "Platelets",
                "result": "240 x10^9/L"
              }
            ]
          },
          {
            "date": "2024-02-13",
            "tests": [
              {
                "name": "CRP",
                "result": "20 mg/L"
              },
              {
                "name": "WBC",
                "result": "7 x10^9/L"
              },
              {
                "name": "Hemoglobin",
                "result": "13 g/dL"
              },
              {
                "name": "Platelets",
                "result": "238 x10^9/L"
              }
            ]
          }
        ],
        "med_orders": [
          {
            "date": "2024-02-10",
            "medication": "Amoxicillin IV",
            "dose": "500 mg",
            "frequency": "8 hourly"
          },
          {
            "date": "2024-02-10",
            "medication": "Paracetamol",
            "dose": "PRN"
          },
          {
            "date": "2024-02-11",
            "medication": "Amoxicillin IV",
            "dose": "250 mg",
            "frequency": "Daily"
          },
          {
            "date": "2024-02-11",
            "medication": "Atorvastatin PO",
            "dose": "20 mg",
            "frequency": "Nightly"
          },
          {
            "date": "2024-02-12",
            "medication": "Amoxicillin IV",
            "dose": "250 mg",
            "frequency": "Daily"
          },
          {
            "date": "2024-02-12",
            "medication": "Atorvastatin PO",
            "dose": "20 mg",
            "frequency": "Nightly"
          },
          {
            "date": "2024-02-13",
            "medication": "Amoxicillin PO",
            "dose": "250 mg",
            "frequency": "Daily"
          },
          {
            "date": "2024-02-13",
            "medication": "Atorvastatin PO",
            "dose": "20 mg",
            "frequency": "Nightly"
          }
        ],
        "notes": [
          {
            "date": "2024-02-10",
            "author": "Dr. Smith",
            "note_type": "Admission Note",
            "content": "Patient admitted with symptoms indicative of pneumonia. Initiated empirical antibiotic therapy."
          },
          {
            "date": "2024-02-11",
            "author": "Dr. Smith",
            "note_type": "Ward Round Note",
            "content": "Patient shows signs of improvement. CRP levels declining. Continue with current antibiotic regimen. Monitor for any adverse reactions."
          },
          {
            "date": "2024-02-12",
            "author": "Dr. Smith",
            "note_type": "Ward Round Note",
            "content": "Patient's temperature normalized. Oxygen saturation levels stable. Plan to switch to oral antibiotics tomorrow."
          },
          {
            "date": "2024-02-13",
            "author": "Dr. Smith",
            "note_type": "Ward Round Note",
            "content": "Patient continues to improve. CRP and WBC trending down. Ready for discharge planning."
          },
          {
            "date": "2024-02-14",
            "author": "Dr. Smith",
            "note_type": "Discharge Summary",
            "content": "Patient's condition improved with treatment. Medically fit for discharge. Home with instructions for oral antibiotics for 5 more days. Follow-up in outpatient clinic in two weeks."
          }
        ]
      },
      {
        "patient_id": "789123",
        "patient_demographics": {
          "name": "Michael Thompson",
          "age": 58,
          "gender": "Male",
          "admission_date": "2024-03-01",
          "discharge_date": "2024-03-06"
        },
        "diagnoses": [
          {
            "date": "2024-03-01",
            "diagnosis_code": "I21.0",
            "description": "Acute transmural myocardial infarction of anterior wall"
          }
        ],
        "encounters": [
          {
            "date": "2024-03-01",
            "type": "Admission",
            "reason": "Severe chest pain, radiating to left arm, shortness of breath"
          },
          {
            "date": "2024-03-01",
            "type": "ECG",
            "findings": "ST-elevation MI (STEMI)"
          },
          {
            "date": "2024-03-01",
            "type": "PCI",
            "description": "Percutaneous Coronary Intervention with stent placement"
          },
          {
            "date": "2024-03-02",
            "type": "Ward Round",
            "notes": "Patient stable, no recurrent chest pain, monitoring continues"
          },
          {
            "date": "2024-03-03",
            "type": "Ward Round",
            "notes": "Vitals stable, patient reports feeling better, troponin levels decreasing"
          },
          {
            "date": "2024-03-04",
            "type": "Ward Round",
            "notes": "Significant improvement, discussing discharge plans and rehabilitation"
          },
          {
            "date": "2024-03-05",
            "type": "Ward Round",
            "notes": "Discharge instructions given, medications prescribed, follow-up scheduled"
          },
          {
            "date": "2024-03-06",
            "type": "Discharge"
          }
        ],
        "labs": [
          {
            "date": "2024-03-01",
            "tests": [
              {
                "name": "Troponin",
                "result": "Elevated, peaking at 12h post admission"
              },
              {
                "name": "CBC",
                "result": "Within normal limits"
              },
              {
                "name": "Lipid Profile",
                "result": "Elevated LDL cholesterol"
              }
            ]
          },
          {
            "date": "2024-03-02",
            "tests": [
              {
                "name": "Troponin",
                "result": "Beginning to decrease"
              }
            ]
          },
          {
            "date": "2024-03-03",
            "tests": [
              {
                "name": "Troponin",
                "result": "Continues to decrease"
              }
            ]
          }
        ],
        "med_orders": [
          {
            "date": "2024-03-01",
            "medication": "Aspirin",
            "dose": "325 mg",
            "frequency": "Once daily"
          },
          {
            "date": "2024-03-01",
            "medication": "Clopidogrel",
            "dose": "75 mg",
            "frequency": "Once daily"
          },
          {
            "date": "2024-03-01",
            "medication": "IV Heparin",
            "dose": "Adjust per protocol",
            "frequency": "Continuous infusion"
          },
          {
            "date": "2024-03-01",
            "medication": "Nitroglycerin",
            "dose": "0.4 mg",
            "frequency": "Every 5 minutes PRN for chest pain"
          },
          {
            "date": "2024-03-02",
            "medication": "Beta-Blocker",
            "dose": "Metoprolol 50 mg",
            "frequency": "Twice daily"
          },
          {
            "date": "2024-03-02",
            "medication": "ACE Inhibitor",
            "dose": "Lisinopril 10 mg",
            "frequency": "Once daily"
          },
          {
            "date": "2024-03-02",
            "medication": "Statin",
            "dose": "40 mg",
            "frequency": "Once daily"
          }
        ],
        "follow_up_care": [
          {
            "type": "Cardiology outpatient clinic",
            "details": "Follow-up appointment scheduled for 2024-03-20 to assess recovery and medication management."
          }
        ],
        "lifestyle_modifications": [
          {
            "recommendation": "Diet",
            "details": "Adopt a heart-healthy diet low in saturated fats, cholesterol, and sodium. Increase intake of fruits, vegetables, and whole grains."
          },
          {
            "recommendation": "Exercise",
            "details": "Gradual reintroduction of physical activity, starting with light walking. Aim to build up to at least 150 minutes of moderate-intensity aerobic activity per week."
          },
          {
            "recommendation": "Smoking cessation",
            "details": "Immediate cessation of smoking. Consider nicotine replacement therapy and counseling to support quitting."
          },
          {
            "recommendation": "Stress management",
            "details": "Explore stress-reducing activities and techniques such as mindfulness, yoga, or meditation. Consider professional support if needed."
          }
        ],
        "notes": [
          {
            "date": "2024-03-01",
            "time": "Morning",
            "note": "Patient admitted and PCI performed. Stable after procedure."
          },
          {
            "date": "2024-03-01",
            "time": "Evening",
            "note": "No recurrent chest pain. Vitals stable. Continue monitoring."
          },
          {
            "date": "2024-03-02",
            "time": "Morning",
            "note": "Patient reports feeling better. Pain management effective. Troponin levels decreasing."
          },
          {
            "date": "2024-03-02",
            "time": "Evening",
            "note": "Stable vitals. Patient in good spirits. No complications noted."
          },
          {
            "date": "2024-03-03",
            "time": "Morning",
            "note": "Significant improvement. Planning for rehabilitation and discharge."
          },
          {
            "date": "2024-03-03",
            "time": "Evening",
            "note": "Discharge planning continues. Patient educated on medication regimen."
          },
          {
            "date": "2024-03-04",
            "time": "Morning",
            "note": "Pre-discharge checks. All medications reviewed. Patient ready for discharge tomorrow."
          },
          {
            "date": "2024-03-05",
            "time": "Morning",
            "note": "Discharge process initiated. Final checks and education completed."
          }
        ]
      },
      {
        "patient_id": "456789",
        "patient_demographics": {
          "name": "Jane Doe",
          "age": 65,
          "gender": "Female",
          "admission_date": "2024-03-10",
          "expected_discharge_date": "2024-03-20"
        },
        "diagnoses": [
          {
            "date": "2024-03-11",
            "diagnosis_code": "I61.9",
            "description": "Intracerebral hemorrhage, unspecified"
          }
        ],
        "encounters": [
          {
            "date": "2024-03-10",
            "type": "Admission",
            "reason": "Fall and subsequent loss of consciousness"
          },
          {
            "date": "2024-03-11",
            "type": "CT Scan",
            "findings": "Hemorrhagic stroke identified in the right hemisphere"
          }
        ],
        "labs": [
          {
            "date": "2024-03-11",
            "tests": [
              {
                "name": "CBC",
                "result": "Hemoglobin slightly low, WBC elevated"
              },
              {
                "name": "Coagulation profile",
                "result": "INR elevated, suggesting prolonged bleeding time"
              }
            ]
          }
        ],
        "med_orders": [
          {
            "date": "2024-03-11",
            "medication": "Mannitol",
            "dose": "0.25 g/kg",
            "frequency": "Every 6 hours"
          },
          {
            "date": "2024-03-11",
            "medication": "Antihypertensives",
            "dose": "Varies",
            "frequency": "As per BP"
          }
        ],
        "ward_round_notes": [
          {
            "date": "2024-03-10",
            "time": "Evening",
            "note": "Patient experienced a fall last night, now with decreased level of consciousness. GCS recorded at 11. Slurring of speech noted."
          },
          {
            "date": "2024-03-11",
            "time": "Morning",
            "note": "CT scan confirms hemorrhagic stroke. Starting mannitol for cerebral edema. Neurological examination: right-sided weakness, continued slurred speech, GCS 11. Patient not safe for discharge, requires close monitoring."
          },
          {
            "date": "2024-03-11",
            "time": "Evening",
            "note": "No significant improvement in neurological status. GCS remains at 11. Patient shows signs of agitation and confusion. Safety measures in place to prevent further falls."
          },
          {
            "date": "2024-03-12",
            "time": "Morning",
            "note": "Patient's condition remains critical. Persistent slurred speech and right-sided weakness. Discussion with family about prognosis and ongoing care needs. Patient not safe for discharge."
          }
        ]
      },
      {
        "patient_id": "000",
        "patient_demographics": {
          "name": "Sean Doe",
          "age": 65,
          "gender": "Male",
          "admission_date": "2024-03-10",
          "expected_discharge_date": "2024-03-12"
        },
        "diagnoses": [
          {
            "date": "2024-03-11",
            "diagnosis_code": "I2101",
            "description": "ST elevation (STEMI) myocardial infarction involving left main coronary artery"
          }
        ],
        "encounters": [
          {
            "date": "2024-03-10",
            "type": "Admission",
            "reason": "CP, SoB, v5-6 ST elevation"
          },
          {
            "date": "2024-03-11",
            "type": "ECG",
            "findings": "v5-6 ST elevation, MONAC given"
          }
        ],
        "labs": [
          {
            "date": "2024-03-11",
            "tests": [
              {
                "name": "Troponin T",
                "result": "30"
              },
              {
                "name": "Troponin T",
                "result": "29"
              }
            ]
          }
        ],
        "med_orders": [
          {
            "date": "2024-03-11",
            "medication": "Morphine",
            "dose": "2-4 mg",
            "frequency": "As needed for pain"
          },
          {
            "date": "2024-03-11",
            "medication": "Oxygen",
            "dose": "2-4 L/min",
            "frequency": "If O2 sat < 90%"
          },
          {
            "date": "2024-03-11",
            "medication": "Nitroglycerin",
            "dose": "0.4 mg",
            "frequency": "Every 5 minutes for 3 doses if pain persists"
          },
          {
            "date": "2024-03-11",
            "medication": "Aspirin",
            "dose": "324 mg",
            "frequency": "Single dose, chewed"
          }
        ],
        "ward_round_notes": [
          {
            "date": "2024-03-10",
            "time": "Evening",
            "note": "Patient presented w/ SoB, CP through ambulance. ECG revealed v5-6 ST elevation. Admit for STEMI."
          },
          {
            "date": "2024-03-10",
            "time": "Evening",
            "note": "Local hospital guidelines indicate PCA. Unable to contact cath lab. Cardio team not responding to bleep.ECG shows persistent ST elevation."
          },
          {
            "date": "2024-03-11",
            "time": "Night",
            "note": "Local hospital guidelines indicate PCA. Unable to contact cath lab. Cardio team not responding to bleep. ECG shows persistent ST elevation."
          },
          {
            "date": "2024-03-12",
            "time": "Night",
            "note": "Patient asks to be discharged because chest pain resolved."
          }
        ]
      }      
      
]

```
