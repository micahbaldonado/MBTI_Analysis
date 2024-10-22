# MBTI Best Questions Analysis

### Overview

This project identifies the **most important questions** for determining a person’s **MBTI type** using data-driven methods. Leveraging open-source MBTI datasets from [Open Psychometrics](https://openpsychometrics.org/tests/OEJTS/comparison/) and applying machine learning techniques, this project evaluates which individual questions are most predictive of a person's MBTI dichotomies:
- **Introversion (I) vs. Extraversion (E)**
- **Sensing (S) vs. Intuition (N)**
- **Thinking (T) vs. Feeling (F)**
- **Judging (J) vs. Perceiving (P)**

The goal is to streamline MBTI assessments, helping users determine personality types with greater accuracy and fewer questions.

### Key Achievements
With just **one question**, I achieved the following accuracy levels in predicting dichotomies:
- **Introversion/Extraversion (I/E)**: 81.6%
- **Sensing/Intuition (S/N)**: 68.2%
- **Thinking/Feeling (F/T)**: 74.4%
- **Judging/Perceiving (J/P)**: 76.9%

### Project Details

- **Dataset**: The analysis is based on responses from the [Open Extended Jungian Type Scales (OEJTS)](https://openpsychometrics.org/tests/OEJTS/comparison/) dataset, which includes an extensive set of response data along with a **codebook** detailing the data formatting.
- **Machine Learning Methods**: I used the **Random Forest Classifier** from **scikit-learn** to determine the most important questions to predict someone’s overall MBTI type, based on feature importance analysis.
  
### Methodology

1. **Data Source**: The [OEJTS dataset](https://openpsychometrics.org/tests/OEJTS/comparison/) provided the core data used in this analysis. The dataset includes participant responses and their associated MBTI types, along with a detailed **codebook** that explains how the data is structured.
2. **Data Preprocessing**:  
   The dataset was thoroughly cleaned and preprocessed to ensure high-quality analysis. Following the instructions from the dataset’s codebook, participants with incomplete or ambiguous data were filtered out using the following criteria:
   - **Invalid percentages**: Participants with percentages lower than 50% on any MBTI dichotomy (Introversion/Extraversion, Sensing/Intuition, Thinking/Feeling, Judging/Perceiving) were excluded, as valid percentages should fall between 50% and 100%.
   - **Ambiguous responses**: Participants who scored exactly 50% on any dichotomy were removed since this indicates equal preference, making the data too ambiguous for accurate modeling.
   - **Missing MBTI types**: Participants who did not complete the survey or were not assigned an MBTI type were removed from the dataset.

   Once the dataset was cleaned, features were engineered to represent each MBTI dichotomy clearly. This preparation ensured the dataset was suitable for machine learning models, focusing on differentiating MBTI types based on participants' responses.

3. **Machine Learning Methods**:  
   Using **scikit-learn**, I applied a **Decision Tree Classifier** to evaluate the impact of each question (feature) in predicting a participant’s MBTI type. While not included in this repository, experimentation with **Random Forest Classifiers** was also conducted to determine the **most important questions/features** for identifying someone's MBTI type as a whole.

### Files

- **`MBTI_best_questions.ipynb`**: The Jupyter notebook containing the full analysis, model training, and results.
- **`OEJTS_dataset.csv`**: The dataset from Open Psychometrics containing MBTI responses and their corresponding types.
- **`codebook.pdf`**: The original codebook explaining the format of the dataset.
- **`question_bank.csv`**: A file containing the questions (organized clearly) from the codebook, which I developed to take up less space in the analysis.
- **`codebook.txt`**: This file contains information regarding the data originally collected and guided the initial data preprocessing steps.

---

### How It Works

1. **Top Questions**: The project identifies the best questions for differentiating each MBTI dichotomy. This allows for a more streamlined assessment process by focusing on the most important questions.
2. **Efficient Personality Typing**: By identifying the key questions, the project simplifies MBTI assessments, reducing the number of questions while maintaining high accuracy.
3. **Decision Tree Classifier**: The model was trained to identify the single most important question that predicts MBTI dichotomies.

---

### Installation and Usage

To replicate the analysis:

1. Clone the repository:

   ```bash
   git clone https://github.com/username/MBTI_best_questions.git
   ```

2. Navigate to the project folder:

   ```bash
   cd MBTI_best_questions
   ```

3. Install required Python packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Run the Jupyter notebook:

   ```bash
   jupyter notebook MBTI_best_questions.ipynb
   ```

---

### Future Work

- **Class Weighting**: Future iterations will incorporate class weighting to address sample bias (overrepresentation of certain types) in the dataset, which would further enhance prediction accuracy.
- **Community Feedback**: I plan to engage with MBTI communities on platforms like Reddit to improve the model based on community feedback and suggestions.

---

### Use Cases

This analysis can be applied in situations where quick, accurate personality typing is useful:
- **Interviews**: Helping interviewers quickly assess personality types and delegate roles.
- **Team Assignments**: In group settings, these key questions can guide team dynamics where synergy is important but time is limited.
- **Public Applications**: This tool can simplify MBTI assessments for people who don’t have the time or patience to complete traditional, long-form tests.

---

### Limitations

- **Self-Selection Bias**: There is heavy self-selection bias in this report. While not included, the distributions of personality type for test takers differs dramatically from test-takers
  - Ex. there is an extremely high occurence of ISFJ (46.9%) after the participants who did not take the test properly were removed
- **Prior MBTI Knowledge**: Test takers who already know what their MBTI type may be influenced by this in how they answer each question
  - 7.79% of participants who took the test correctly dedicated 21 or more hours to MBTI typology. These participants can easily determine which questions target which dichotomy, which could influence how they respond.

---

### License

This project is licensed under the MIT License - see the LICENSE file for details.

---

### Acknowledgments

- **Open Psychometrics**: The dataset used in this project was provided by Open Psychometrics through the [OEJTS dataset](https://openpsychometrics.org/tests/OEJTS/comparison/).
- **Community Contributions**: Special thanks to the open-source community for their work on the dataset and tools used in this analysis.

---

### Contact

Feel free to reach out for questions, suggestions, or potential collaborations:

**Micah Baldonado**  
Carnegie Mellon University  
micahbaldonado@gmail.com
