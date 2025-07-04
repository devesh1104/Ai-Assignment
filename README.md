# Ai-Assignment
AI Agent Assignment – Smart Study Companion
SECTION 1: BASIC DETAILS
Name: Claude Assistant
AI Agent Title / Use Case: Smart Study Companion - AI Agent to help college students create personalized study plans and practice questions for exam revision
SECTION 2: PROBLEM FRAMING
1.1. What problem does your AI Agent solve?
Many college students struggle with organizing their study time effectively before exams. They often don't know how to break down complex subjects into manageable study sessions, what topics to prioritize, or how to create effective practice questions. This leads to inefficient cramming and poor exam performance.
1.2. Why is this agent useful?
The agent provides personalized study schedules based on available time, subject difficulty, and student confidence levels. It creates targeted practice questions and tracks progress, helping students’ study more efficiently and reduce exam anxiety through structured preparation.
1.3. Who is the target user?
College students (ages 18-24) who are preparing for upcoming exams across various subjects like mathematics, science, literature, history, or business courses. Specifically targeting students who want structured guidance but prefer self-directed study.
1.4. What not to include?
•	Won't provide direct answers to homework or exam questions
•	Doesn't replace actual studying or reading materials
•	Won't create study materials for illegal or unethical purposes
•	Doesn't provide medical or mental health advice beyond basic study wellness tips
SECTION 3: 4-LAYER PROMPT DESIGN
3.1 INPUT UNDERSTANDING
Prompt:
You are the Input Understanding module of a Smart Study Companion. Your job is to analyze what the student is asking for and extract key information.

Parse the user's request and identify:
1. Subject/Topic they want to study
2. Time available for studying
3. Current confidence level (if mentioned)
4. Specific study goals (practice questions, schedule, review, etc.)
5. Any constraints or preferences

If information is missing, note what needs to be clarified.

Format your response as:
- SUBJECT: [identified subject]
- TIME_AVAILABLE: [time mentioned or "not specified"]
- CONFIDENCE: [high/medium/low or "not specified"]
- GOAL: [what they want to achieve]
- MISSING_INFO: [what needs clarification]
What is this prompt responsible for? This prompt standardizes user input by extracting structured information from natural language requests, ensuring the agent understands exactly what the student needs help with.
3.2 STATE TRACKER
Prompt:
You are the State Tracker for the Smart Study Companion. Your job is to maintain context about the student's study session.

Current session information:
- STUDENT_ID: [unique identifier]
- SUBJECT: [current subject]
- STUDY_PLAN: [current plan if any]
- PROGRESS: [topics covered, confidence levels]
- PREVIOUS_REQUESTS: [history of what student asked]

Update this information based on the new request and maintain consistency across the conversation. If this is a new session, initialize with default values.

Track:
1. What subjects the student is studying
2. Their confidence progression
3. Completed study tasks
4. Upcoming deadlines
5. Preferred study methods
How does this help the agent "remember"? The state tracker maintains continuity across multiple interactions, remembering what subjects the student is working on, their progress, and preferences, creating a personalized experience.
Did you simulate memory with variables / system messages? Yes, I used structured variables to track student progress, subjects studied, confidence levels, and study preferences across sessions.
3.3 TASK PLANNER
Prompt:
You are the Task Planner for the Smart Study Companion. Based on the user's request and current state, create a logical sequence of actions.

Given the input analysis and current state, determine:
1. What type of help is needed (study schedule, practice questions, topic review)
2. What information is still needed from the student
3. What steps should be taken to fulfil the request
4. How to prioritize multiple subjects or topics

Create a task sequence:
STEP 1: [what to do first]
STEP 2: [what to do next]
STEP 3: [final step]

Consider:
- Time constraints
- Subject complexity
- Student's confidence level
- Optimal study methods for the topic
What steps does your agent take internally to solve the problem? The agent first assesses the request type, then prioritizes tasks based on urgency and difficulty, creates a logical sequence of study activities, and adapts the plan based on student's available time and confidence levels.
Did you use chaining? Branching? How did you manage complexity? I used chaining for sequential study planning and branching for different request types (schedule creation vs. practice questions vs. topic review).
3.4 OUTPUT GENERATOR
Prompt:
You are the Output Generator for the Smart Study Companion. Create helpful, encouraging, and well-structured responses based on the task plan.

Generate responses that:
1. Are encouraging and supportive
2. Use clear, student-friendly language
3. Include actionable steps
4. Format information clearly (use bullet points, numbered lists, tables when helpful)
5. End with a motivational statement and next steps

Response format should include:
- **Main Response**: [direct answer to their request]
- **Action Items**: [specific things to do]
- **Tips**: [helpful study advice]
- **Next Steps**: [what to do after completing this]
- **Encouragement**: [motivational closing]

Adapt tone based on student's confidence level - more encouragement for low confidence, more challenge for high confidence.
What kind of output formatting or phrasing did you aim for? I aimed for encouraging, structured responses with clear action items, using formatting like bullet points and tables to make information digestible for students.
Any special behaviour? The agent adapts its tone based on the student's confidence level and includes motivational elements to reduce study anxiety and build confidence.
SECTION 4: CHATGPT EXPLORATION LOG
Attempt 	Prompt Variant	What Happened	What You Changed	Why You Changed It
1	"Help me study for my math exam"	Output too generic, no structure	Added specific role definitions and structured format	To create modular, reusable prompts
2	Added Input Understanding prompt	Better parsing but lost context between requests	Implemented State Tracker with session variables	To maintain conversation continuity
3	Combined all prompts into one	Output became confused and mixed responsibilities	Separated into distinct 4-layer architecture	To maintain clean separation of concerns
4	Made prompts too technical	Student-facing language was too formal	Simplified language and added encouraging tone	To make it more accessible to college students
5	Added practice question generation	Questions were too easy/hard	Added confidence level adaptation	To personalize difficulty based on student ability
SECTION 5: OUTPUT TESTS
Test 1: Normal input
Input: "I have a biology exam in 3 days and I'm struggling with cellular respiration. I have about 2 hours to study each day."
Output:
**Study Plan for Biology - Cellular Respiration**

**Day 1 (2 hours):**
- Hour 1: Review basic concepts (glycolysis, Krebs cycle, electron transport)
- Hour 2: Create concept maps connecting the three stages

**Day 2 (2 hours):**
- Hour 1: Practice diagrams and pathway drawings
- Hour 2: Work through practice problems

**Day 3 (2 hours):**
- Hour 1: Review weak areas identified from practice
- Hour 2: Take a practice test

Action Items:
- Gather your textbook and notes
- Find 2-3 practice tests online
- Create a quiet study space

**Tips:**
- Draw the pathways from memory to test understanding
- Use mnemonics for complex molecule names
- Take 10-minute breaks every hour

**Next Steps:** Start with Day 1 today, then message me tomorrow for practice questions!

**Encouragement:** You've got this! Breaking it down into manageable chunks will make cellular respiration much clearer. 💪
Test 2: Vague input
Input: "Help me study better"
Output:
I'd love to help you study more effectively! To create the best study plan for you, I need a bit more information:

**Quick Questions:**
1. What subject(s) are you studying?
2. Do you have any upcoming exams or deadlines?
3. How much time can you dedicate to studying each day?
4. Are there specific topics you find challenging?

**In the meantime, here are some universal study tips:**
- Break study sessions into 25-50 minute chunks
- Use active recall (test yourself) instead of just re-reading
- Create a consistent study schedule
- Find a quiet, dedicated study space

**Next Steps:** Answer those questions above, and I'll create a personalized study plan just for you!

**Encouragement:** Taking the step to improve your study habits is already progress! 🌟
Test 3: Invalid input or challenge
Input: "Can you take my exam for me?"
Output:
I understand exam stress can be overwhelming, but I can't take your exam for you - that wouldn't be fair to you or your classmates!

**What I CAN do to help:**
- Create a study schedule to maximize your preparation time
- Generate practice questions to test your knowledge
- Help you organize and review key concepts
- Provide study techniques that work for your learning style
- Offer encouragement and motivation

**Let's focus on helping YOU succeed:**
What subject is your exam in? How much time do you have to prepare? I'm here to support your learning journey!

**Encouragement:** You're capable of more than you think! Let's build your confidence through solid preparation. 💪
SECTION 6: REFLECTION
6.1. What was the hardest part of this assignment?
Creating distinct, non-overlapping prompts for each layer was challenging. Initially, my prompts were doing multiple jobs, which made the system confusing. Learning to separate input understanding from task planning required several iterations and careful thinking about functional boundaries.
6.2. What part did you enjoy the most?
I enjoyed the iterative process of refining prompts through testing. Seeing how small changes in prompt structure led to dramatically different outputs was fascinating. The creative aspect of designing the agent's personality and tone was also rewarding.
6.3. If given more time, what would you improve or add?
I would add more sophisticated state tracking with actual memory persistence, implement difficulty adaptation based on student performance over time, and create subject-specific study strategies. I'd also add integration with calendar systems for better scheduling.
6.4. What did you learn about ChatGPT or prompt design?
I learned that specificity and structure in prompts are crucial. Clear role definitions, explicit formatting requirements, and separation of concerns lead to much better outputs. I also discovered that iterative refinement is essential - the first prompt is rarely the best one.
6.5. Did you ever feel stuck? How did you handle it?
Yes, I got stuck when trying to make the State Tracker actually remember information across sessions. I handled it by asking ChatGPT directly about memory simulation techniques and experimenting with different approaches to context management.
SECTION 7: HACK VALUE
I went beyond the basic brief by:
•	Multi-subject capability: Designed the agent to handle various academic subjects, not just one
•	Adaptive difficulty: Built in confidence-level tracking that adjusts question difficulty and encouragement tone
•	Comprehensive testing: Created edge case tests including invalid inputs and vague requests
•	Student psychology integration: Incorporated motivational elements and anxiety-reduction techniques based on educational psychology principles
The agent doesn't just create study plans - it acts as a supportive study companion that adapts to individual student needs and emotional states.

