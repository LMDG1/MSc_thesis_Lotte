# MSc_thesis_Lotte

This repository belongs to the thesis that explores the influence of explainable AI score suggestions on teachers' (scoring) behavior and cognitive load. It contains a collection of Python notebooks that were used to either:
1) Create the student response dataset for the digital scoring environment (see Dataset_creation folder)
2) Analyze how teachers interact with an XAI-assisted scoring environment (see Data_analysis folder).

## 1. Dataset creation notebooks 
### Feature_importance.ipynb
This notebook implements Local Interpretable Model-agnostic Explanations (LIME) to identify key features in student responses that influence scoring decisions:
- Uses a multilingual S-BERT model (paraphrase-multilingual-MiniLM-L12-v2) to encode Dutch student responses
- Calculates cosine similarity between student responses and model answers
- Uses LIME to highlight words or phrases most influential in matching responses to expected answers
- Creates visualizations showing feature importance for each response part
- Generates HTML explanations that can be integrated into a teacher assessment interface

### Similar_answers.ipynb
This notebook creates "Similar Answer" XAI features by identifying semantically similar student responses:
- Utilizes the same S-BERT model to create vector embeddings of student responses
- Calculates semantic similarity between responses using cosine similarity
- Identifies and displays the most similar responses to a given answer
- Presents similarity scores and distributions of scores (correct/incorrect) for similar responses

## 2. Data analysis notebooks
### Nasatlx_scores_analysis.ipynb
This notebook examines cognitive load using NASA Task Load Index (NASA-TLX) ratings:
- Compares cognitive load between XAI and non-XAI scoring interfaces
- Creates radar charts showing individual NASA-TLX profiles for each teacher
- Analyzes differences in cognitive load dimensions (mental demand, frustration, effort, etc.)
- Compares load differences between Biology and Economics teacher groups

### Interaction_data_analysis.ipynb
This notebook analyzes teacher interaction patterns with the XAI system:
- Tracks when and how frequently teachers use "Why?" and "Similar Answer" buttons
- Compares interaction patterns between Biology and Economics teachers
- Analyzes interaction differences between Type A (ambiguous/gray area) and Type B (straightforward) student responses
- Uses Bayesian analysis to quantify the relationship between response complexity and XAI feature usage
- Correlates interaction frequency with cognitive load differences

### Inter_rater_reliability_analysis.ipynb
This notebook analyzes inter-rater reliability (IRR) between benchmark scores and teachers' scores:
- Calculates Cohen's Kappa and raw agreement percentages between teacher scores and benchmark scores
- Compares reliability differences between XAI-interacted vs. non-interacted responses
- Evaluates IRR for Type A vs. Type B responses
- Analyzes reliability differences between Biology and Economics teachers
