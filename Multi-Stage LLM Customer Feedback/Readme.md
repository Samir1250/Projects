**Problem Statement**  
Detect recurring customer issues from support feedback and recommend concrete actions for the business. 

**Assumptions:**

- Each message belongs to exactly one theme.

- Themes are concise (≤5 words) and recurring across multiple messages.

**Set up** 

1. Clone the repository from Git Within your Databricks Workspace  
2. Install Dependencies “pip install pyspark pandas seaborn matplotlib huggingface\_hub”  
3. Create a developer token to securely authenticate your identity and authorize access to hosted models(“Hugging Face”)  
4. Upload your data into the Catalog within Databricks to begin with the Notebook  
   

**How to Run**   
Head to Customer\_Feedback\_Theme\_Analysis.ipynb and run the following cells

**Part 1:** Data Processing & Analysis (Code)  
**Part 2:**  Results & Deliverables

**Decisions and Trade-Offs**

- Databricks provides unified platform for data processing and LLM classification  
- Quick start as databricks is able to infer schema and ingest into tabular format  
- For increased safety in production, we could use Azure Key Vault to store API tokens, keeping them hidden from plain code for security  
- Chose to let the LLM pick the 3-5 best categories vs hard coding options  
  


**Final Feature Decision Process**

- **customer\_id**: Uniquely identifies each customer  
- **message**: Contains the customer feedback  
- **theme**: Summarizes the main categories by sentiment  
- **created\_at**: Captures when the message was submitted  
- **total\_spend**: Indicates customer value  
- **subscription\_tier**: Provides context on the customer’s service level

**Further Improvements**

* Modularize code by splitting ingestion, LLM calls, classification, and visualization into separate files for maintainability and readability.

* Upgrade to more robust LLMs, such as GPT-5, or Claude Sonnet, to improve theme extraction accuracy and generate more nuanced recommendations.

* Implement multi-label classification to capture messages that belong to multiple themes simultaneously.

* Improve data quality in the product\_usage table by handling nulls and inconsistent values before merging with feedback to ensure accurate analysis.

* Automate anomaly detection to flag sudden spikes in negative sentiment in real-time.

