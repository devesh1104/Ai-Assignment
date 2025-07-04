
# 📚 Claude Assistant – Smart Study Companion

**AI Agent Title / Use Case**: Smart Study Companion - AI Agent to help college students create personalized study plans and practice questions for exam revision

---

## SECTION 1: BASIC DETAILS

- **Name**: Claude Assistant  
- **Use Case**: Personalized Study Plans & Practice Questions for Exam Revision

---

## SECTION 2: PROBLEM FRAMING

### 1.1 What problem does your AI Agent solve?
Many college students struggle with organizing their study time effectively before exams. They often don't know how to break down complex subjects into manageable study sessions, what topics to prioritize, or how to create effective practice questions. This leads to inefficient cramming and poor exam performance.

### 1.2 Why is this agent useful?
The agent provides personalized study schedules based on available time, subject difficulty, and student confidence levels. It creates targeted practice questions and tracks progress, helping students’ study more efficiently and reduce exam anxiety through structured preparation.

### 1.3 Who is the target user?
College students (ages 18-24) preparing for exams across various subjects like mathematics, science, literature, history, or business. It especially supports self-directed students who seek structured guidance.

### 1.4 What not to include?
- Won't provide direct answers to homework or exam questions
- Doesn't replace actual studying or reading materials
- Won't create study materials for illegal or unethical purposes
- Doesn't provide medical or mental health advice beyond basic study wellness tips

---

## SECTION 3: 4-LAYER PROMPT DESIGN

### 3.1 INPUT UNDERSTANDING

**Prompt**:  
You are the Input Understanding module of a Smart Study Companion. Your job is to analyze what the student is asking for and extract key information.

**Extracted Fields**:
- SUBJECT: [identified subject]  
- TIME_AVAILABLE: [time mentioned or "not specified"]  
- CONFIDENCE: [high/medium/low or "not specified"]  
- GOAL: [what they want to achieve]  
- MISSING_INFO: [what needs clarification]

**Purpose**: Standardizes user input to ensure accurate task planning.

---

### 3.2 STATE TRACKER

**Prompt**:  
You are the State Tracker. Maintain session context with variables like:  
- STUDENT_ID  
- SUBJECT  
- STUDY_PLAN  
- PROGRESS  
- PREVIOUS_REQUESTS  

**Tracks**:
1. Subjects studied
2. Confidence progression
3. Completed tasks
4. Upcoming deadlines
5. Preferred study methods

**Memory Simulation**: Yes, using structured state variables.

---

### 3.3 TASK PLANNER

**Prompt**:  
Create a task sequence using available time and confidence levels.  

**Determine**:
1. Help type (schedule, practice, review)  
2. Information needed  
3. Logical action steps  
4. Priority logic

**Output Example**:
```
STEP 1: [Initial step]  
STEP 2: [Next step]  
STEP 3: [Final step]
```

**Technique**: Uses chaining and branching for logical planning.

---

### 3.4 OUTPUT GENERATOR

**Prompt**:  
Craft encouraging, clear responses with:
- **Main Response**  
- **Action Items**  
- **Tips**  
- **Next Steps**  
- **Encouragement**  

**Formatting**: Lists, tables, emojis, motivational tone based on confidence level.

---

## SECTION 4: CHATGPT EXPLORATION LOG

| Attempt | Prompt Variant | What Happened | What You Changed | Why You Changed It |
|---------|----------------|----------------|-------------------|---------------------|
| 1 | "Help me study for my math exam" | Output too generic | Added specific role definitions | For modular prompts |
| 2 | Added Input Understanding prompt | Lost context | Implemented State Tracker | To maintain session state |
| 3 | Combined all prompts into one | Output mixed roles | Separated 4-layer design | Cleaner responsibility separation |
| 4 | Technical language | Too formal | Simplified tone | To fit student audience |
| 5 | Added practice generation | Mismatched difficulty | Adapted to confidence level | For personalization |

---

## SECTION 5: OUTPUT TESTS

### ✅ Test 1: Normal Input

**Input**: "I have a biology exam in 3 days and I'm struggling with cellular respiration. I have about 2 hours to study each day."

**Output**: 3-Day Study Plan with detailed breakdowns, action items, study tips, and encouragement.

---

### 🟡 Test 2: Vague Input

**Input**: "Help me study better"  
**Output**: Clarifying questions, general tips, motivation

---

### ❌ Test 3: Invalid Input

**Input**: "Can you take my exam for me?"  
**Output**: Ethical rejection, suggestions for how the agent *can* help, supportive language

---

## SECTION 6: REFLECTION

### 6.1 Hardest Part:
Separating overlapping prompt functions into distinct, modular components.

### 6.2 Most Enjoyable:
Iterative testing and prompt refinement. Designing the agent’s tone.

### 6.3 If Given More Time:
- Add persistent memory
- Calendar integration
- Subject-specific strategies

### 6.4 What I Learned:
- Importance of structured, modular prompt design
- Clear role definitions improve output quality
- Prompt refinement is essential

### 6.5 When Stuck:
When memory simulation became confusing, consulted ChatGPT and tried context experiments.

---

## SECTION 7: HACK VALUE

- Multi-subject support
- Confidence-based question difficulty
- Edge case handling (vague, invalid, unethical)
- Student psychology elements (encouragement, anxiety reduction)

> This isn’t just a study tool. It’s a **personalized, motivational companion** for students to succeed on their own terms.

---
