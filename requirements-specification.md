### **AI-Based Skin Disease Detection: Requirements Specification**

#### **Table of Contents**
- [1. Project Statement](#1-project-statement)
- [2. Stakeholders and User Groups](#2-stakeholders-and-user-groups)
- [3. Motivation for Use](#3-motivation-for-use)
- [4. Example Use Scenario](#4-example-use-scenario)
- [5. Requirements Analysis](#5-requirements-analysis)
  - [5.1 Functional Requirements](#51-functional-requirements)
  - [5.2 Non-functional Requirements](#52-non-functional-requirements)
- [6. Technical and Software Constraints](#6-technical-and-software-constraints)
- [7. Evaluation Criteria](#7-evaluation-criteria)
- [8. Additional Considerations](#8-additional-considerations)

---

## **1. Project Statement**

The AI-Based Skin Disease Detection application is a mobile-based solution designed to assist users in identifying potential skin conditions by analyzing images of skin lesions. Users can capture/upload photos of affected skin areas, which are then processed in the cloud using a machine learning classification model trained on the **ISIC dataset** and other dermatology datasets to distinguish between common conditions such as melanoma, psoriasis, and eczema. The application provides a probability score for each classification, allowing users to take further steps such as consulting a dermatologist.

The system aims to enhance early detection, provide preliminary guidance, and raise awareness of dermatological conditions while ensuring data privacy and compliance with medical safety standards.

---

## **2. Stakeholders and User Groups**

1. **End Users (Patients & General Public)**  
   - Individuals experiencing skin abnormalities seeking preliminary assessment.
   - People looking for awareness of common skin conditions before consulting a doctor.

2. **Regulatory Bodies & Healthcare Institutions**
   - Ensuring compliance with medical data privacy laws (e.g., GDPR, HIPAA).
   - Overseeing AI-based health applications to meet medical safety standards.

3. **Dermatologists & Medical Professionals**  (Low Priority)  
   - Can use the tool as a pre-screening aid to support patient diagnosis.
   - Provide feedback to improve the accuracy and reliability of the AI model.


---

## **3. Motivation for Use**

- **Early Detection & Awareness**  
  Provides users with preliminary insight into possible skin conditions, prompting them to seek medical advice early.

- **Convenience & Accessibility**  
  Allows individuals to assess their skin health without an immediate doctor visit.

- **AI-Powered Assistance**  
  Utilizes deep learning to enhance accuracy and provide more data-driven insights than traditional self-diagnosis. Because some traditional self-diagnosis methods lead to unnecessary stress and anxiety for the patient due to misdiagnosis that they did.

- **Support for Medical Professionals**  (Low Priority, not sure how to implement)  
  Dermatologists can use the tool for preliminary analysis and streamline patient consultations.

---

## **4. Example Use Scenario**

### **4.1 User Story**

> Mickey notices an irregular mole on his arm. Concerned about skin cancer, he downloads the AI-Based Skin Disease Detection app and takes a clear photo of the affected area. The app uploads the image to the cloud, where a pre-trained ML model processes it. The results indicate a high probability of melanoma with a 90% confidence score. The app advises Mickey to consult a dermatologist for further evaluation. He immediately books an appointment, leading to early diagnosis and treatment.

### **4.2 UML Use-Case Diagram**
<img width="833" alt="Screenshot 2025-03-16 at 18 05 52" src="https://github.com/user-attachments/assets/59731ec6-30cb-42f0-b1c8-0d3c55c3b890" />


---

## **5. Requirements Analysis (Volere Template)**

### **5.1 Functional Requirements**

1. **User Interaction & Image Capture/Upload**
   - Description: Users should be able to capture/upload images of skin lesions for classification.
   - Rationale: Essential for AI-based detection.
   - Fit Criterion: The app allows image capture or upload.

2. **User Account Management**
   - Description: Users should be able to create accounts, log in, and manage their profile.
   - Rationale: Enables personalized experience and history tracking.
   - Fit Criterion: Users can sign up, log in via Firebase Authentication, and update profile information.

3. **Image Processing & AI Model Integration**
   - Description: The system must classify skin conditions using an AI model trained on the ISIC dataset.
   - Rationale: Enables accurate disease detection.
   - Fit Criterion: Model classifies images into predefined categories with a probability score.

4. **Result Presentation & User Guidance**
   - Description: The app must present results in a user-friendly format.
   - Rationale: Enhances usability and interpretation.
   - Fit Criterion: Results are color-coded with confidence levels and medical advice.

5. **Security & Compliance**
   - Description: Ensures authentication, access control, and data security.
   - Rationale: Protects sensitive medical data.
   - Fit Criterion: Implements Firebase Authentication, encryption, and access control measures.

---

### **5.2 Non-functional Requirements**

1. **Performance**
   - Description: The classification process should be efficient and finish at a reasonable time.

2. **Accuracy & Reliability**
   - AI predictions must be reliable.

3. **Data Privacy & Security**
   - Ensures authentication, access control, data confidentiality, and integrity.

---

## **6. Technical and Software Constraints**

- **Operating System:** Android & iOS  
- **Programming Languages:**  
  - **Frontend:** Flutter (Dart)  
  - **Backend:** Python (Flask/FastAPI)  
- **ML Model & Services:**  
  - Various Datasets, Roboflow, Google Cloud AutoML Vision, AWS Rekognition Custom Labels, or Microsoft Custom Vision. (Undecided, still evaluating my options, but I will prioritize Roboflow)
- **Database & Storage:**  
  - **Cloud-based image storage (Wondering if I should store an encrypted version of the images and I have to determine their lifespan)**  
- **Security:**  
  - **End-to-end encryption** for data transmission  
  - **Firebase Authentication** for secure access  
  - **Role-based access control (RBAC) to restrict access based on user roles**

---

## **7. Evaluation Criteria**

- **Quality & Accuracy**: AI classification precision and recall metrics.
- **Performance**: Response time and system stability.
- **User Experience**: Accessibility compliance and user feedback.

---

## **8. Additional Considerations**

- **Medical Disclaimer:** The app should clearly state that it is not a replacement for professional diagnosis.
- **Model Improvement:** Future updates could incorporate real-time dermatologist feedback to retrain the AI model.

