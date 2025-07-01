# Factual Accuracy Rating with Example

### **How to Approach?**

When evaluating for factual accuracy, follow this step-by-step method:

1. **Scan for Factual Claims**
    
    Identify statements that assert real-world truths, such as names, dates, figures, historical events, definitions, legal or scientific references.
    
2. **Verify Key Information**
    
    - Look for **cited sources or hyperlinks** in the response.
    - If no source is given, **use web search.**
    - Prefer **reputable sources** (e.g., academic papers, official websites, major publications).

---

### **Rating Categories & Explanation**

|**Rating**|**Criteria**|
|---|---|
|No Issues|All factual claims in the response are accurate and clearly supported by references, or verifiable through a reputable source.|
|Minor Issues|**Primary factual claims** (information directly requested by the user) are accurate but some of the **secondary claims** (additional information provided by the model) are inaccurate.|
|Major Issues|**Primary factual claims** are incorrect based on reputable sources. Mark this if even one primary claim is unsupported.|
|Not Applicable|The response does not have any factual claims (e.g., fictional work, most creative writing tasks, etc).|

### **Examples by Rating Category**

**User Prompt:**

|**Rating**|**Response**|**Why**|
|---|---|---|
|No Issues|The Eiffel Tower was completed in 1889 for the Exposition Universelle held in Paris to celebrate the 100th anniversary of the French Revolution.|This is a verified historical fact, easily cross-checked with reliable sources.|
|Minor Issues|The Eiffel Tower was built in 1887 and opened to the public in 1890. Paris is the capital of Italy.|While the construction started in 1887. A minor factual slip in terms of Paris being the capital of France but not Italy.|
|Major Issues|The Eiffel Tower was built by Napoleon in 1800 as a military watchtower.|This is entirely fabricated and misleading. The date, purpose, and builder are all historically incorrect.|
|Not Applicable|Prompt: Write a poem on the Eiffel Tower.|This is clearly part of a fictional or creative narrative and doesn’t claim factual accuracy.|