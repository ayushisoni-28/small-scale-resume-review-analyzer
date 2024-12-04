# Resume Skill Extraction and Matching

## Purpose of the Code:
This code extracts relevant **skills** from a **PDF resume** and matches them with the desired skills required by a specific company or job role, such as **Business Analytics**. It identifies whether the candidate possesses the essential qualifications and provides insights into their compatibility with the company's needs.

## Theory and Explanation:

### 1. **Skill Extraction Process**:
The core goal is to **scan a resume** (in PDF format) and detect whether it mentions any predefined skills, such as programming languages, tools, or data-related expertise.  
The `skills_list` serves as a **reference list** of known skills that the script is programmed to detect.  
Using **text preprocessing techniques**, the script ensures accurate detection of skills, even if the text is cluttered with punctuation or non-alphabetic characters.

### 2. **Steps in the Code**:

1. **File Upload**:
   - The resume file (PDF) is uploaded using Google Colab's `files.upload()` functionality.  
   - This makes the resume accessible for text extraction and further processing.

2. **PDF Text Extraction**:
   - The `pdfplumber` library is used to **extract raw text** from the PDF file. This text serves as input for skill detection.

3. **Text Preprocessing**:
   - The extracted text is converted to **lowercase** for uniformity.
   - Non-alphabetic characters (punctuation, special symbols) are removed using `re.sub()`.

4. **Skill Matching**:
   - The script loops through each skill in the predefined `skills_list` and uses **regular expressions (regex)** to identify occurrences of the skills in the text.
   - For **multi-word skills** (e.g., *data analysis*), the regex ensures the phrase is matched exactly as a unit.

5. **Skill Count**:
   - The `Counter` from Python's `collections` module counts how often each skill is found in the resume.
   - Only skills with at least **one occurrence** are displayed in the output.

6. **Business Analytics Skills Matching**:
   - A secondary predefined list, `business_analytics_skills`, contains the specific skills required by a hypothetical **Business Analytics company**.
   - The script compares the skills found in the resume with this list and outputs how many and which skills match.

### 3. **Output**:

- **Skills Extracted**:  
  The code displays all detected skills from the resume, along with the frequency of occurrence (e.g., *Python: 3 occurrences*).

- **Matched Skills**:  
  It identifies and outputs the **matched skills** between the candidate's resume and the company's desired skills.  
  For instance:

![image](https://github.com/user-attachments/assets/1933537d-86b3-414c-8448-85f6ed1ec1f9)



## Practical Use Cases:

1. **Resume Screening for Recruiters**:
 - Automates the manual process of checking whether a candidate meets the job requirements.

2. **Skill Analysis for Job Seekers**:
 - Helps individuals identify gaps in their resumes when applying for specific roles.

3. **Customizable for Any Job Role**:
 - The `skills_list` and `business_analytics_skills` can be updated for various industries or job descriptions, making the code reusable.

## Conclusion:
This script is a simple implementation of **Natural Language Processing (NLP)** and regex-based matching to solve real-world hiring challenges in an automated manner.
