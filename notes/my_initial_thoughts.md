Problem: How do we define a robust LLM as a judge evaluator to evaluate request -> LLM -> response workflows?
Proposed Approach: 
- Dataset Acquisition: Find a dataset containing coding instructions (request), LLM-generated solutions (response), and human annotations indicating whether the solution meets the requirements.
- Problem Definition: Define the request -> LLM -> response problem formally. Also define the response evaluator, the request to response evaluator, and the request evaluator formally and figure out the state of research for all. 
- Evaluator Definition: Define the components of an evaluator, which will assess the alignment between request and response.
- Evaluator Construction: Using the defined components, construct evaluators using different methods.
    - Purpose Defintion: What types of applications are LLMs as a Judge applied to? 
- Define Evaluator Evaluation Metrics: To be able to compare the evaluators, we need to define metrics that enable us to do this. 
    - Initial thoughts: 
        - Accuracy = How well does the evaluator’s assessment adhere to the “optimal” human assessment?
        - Interpretability = …
- Open Challenges: ??
Project => Evaluation and Comparison: The evaluators will be applied to the dataset, and its performance will be compared against human evaluations using appropriate metrics.


X = When signal A changes from true to false, then signal B should be set to 3. (evaluation input + C)
X2 = When is christmas? (Expection Handling)
C = Signal A can have values true, false, unset. 
Y1 = def function(): (evalution output)
    if A == true:
        B = 3. 

Y2 = def function(): 
    # This function checks signal A.
    if A == true: 
        B = 3.




\subsection{Objective Signals vs Judge Scores (Functional Correctness)}
For code, execution-based evaluation remains critical: HumanEval defines correctness as passing predefined tests~\citep{chen2021evaluating}. However, execution-only misses requirement adherence and style; combining objective signals with judge scores balances efficiency and coverage~\cite{li2024_llmsasjudges}.

\subsection{Robustness, Bias, and Consistency}
Meta-evaluations test stability under order/paraphrase perturbations and across languages/domains. Evidence shows order sensitivity and formatting effects in pairwise judging~\cite{zheng2023judgelm}, multilingual variability~\cite{hada2024metal}, and slice-dependent reliability~\cite{bavaresco2024judgebench}. Fairness analysis along HELM-style axes helps reveal subgroup disparities~\cite{liang2022helm}. Preference-focused works further examine pairwise reliability and aggregation~\cite{liu2024pairs}.