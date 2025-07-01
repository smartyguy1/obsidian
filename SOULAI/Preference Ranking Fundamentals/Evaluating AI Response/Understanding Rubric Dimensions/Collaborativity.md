### How to Approach

To evaluate collaborativity:

1. Check the user prompt and assess if it needs collaboration.
2. If it does not require collaboration, mark it as N/A.
3. If it requires collaboration, check how well the response demonstrates assistance.

❗Collaborativity is not required on all questions. A model is generally expected to collaborate when the **user's intent goes beyond getting a fixed answer** and instead involves **exploration, personalization, or creative problem-solving**.

---

### **Rating Categories & Explanation**

|**Rating**|**What It Means**|
|---|---|
|**No Issues**|The model is clearly collaborative—it encourages the ongoing conversation through follow-ups, personalised suggestions, clarifications based on likely user needs.|
|**Minor Issues**|The model has generally collaborated with the user. However, the follow-ups or suggestions are generic and not personalised to the user intent.|
|**Major Issues**|The response is overly prescriptive. It does not encourage interaction and completely misses out on the required collaboration.|
|**Not Applicable**|The task does not require collaboration.|

### **Examples by Rating Category**

**User Promp**t: "I’m designing a landing page. How should I organise the content?”

| **Rating**     | **Response**                                                                                                                                                                                                                                                                                                                                                                | **Why**                                                                                                                                                                                                  |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| No Issues      | “Great! That’s an exciting project. <br><br>One common structure is: A clear headline that conveys your value proposition.<br><br>A subheading with supporting detail.<br><br>A visual or demo section. Social proof (like testimonials).<br><br>A strong call-to-action. <br><br>What kind of audience are you designing for? I can help tailor the layout based on that.” | Provides useful, structured advice and invites the user into a co-creative dialogue. Encourages further input and adapts based on context. Feels like an open-ended, collaborative exchange. → No Issues |
| Minor Issues   | “You’ll want to include a strong headline, a brief value proposition, a section with visuals, some testimonials, and a clear CTA at the end. This structure helps guide users through the page efficiently.<br><br>Let me know if there’s anything else I can help with!”                                                                                                   | The follow-up is too open-ended/generic ("anything else I can help with?") rather than engaging with the actual topic. → Minor Issues                                                                    |
| Major Issues   | “You should include a headline, a short subheading, a section with visuals, a few testimonials, and a strong call-to-action at the end.”                                                                                                                                                                                                                                    | • The structure and content are technically correct. <br><br>• However, there is no follow-up, no invitation to continue, no openness to user preferences or further input. → Major Issues               |
| Not Applicable | Prompt: “What is the distance between Hyderabad and Delhi?”                                                                                                                                                                                                                                                                                                                 | There’s no scope for collaboration in fact-based, one-line queries, where the response can be generated at one go.                                                                                       |

