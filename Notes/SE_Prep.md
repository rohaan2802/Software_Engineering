# Software Engineering Exam Prep

## Prototype Model

Prototype Model in software development means:  
A rough working sample (demo version) of software is made first to show the client how the system will look  
and work.  
The client checks it, gives feedback, and developers improve it again and again until final software is built.  
Simple Example:  
Suppose you want a food delivery app.  
Instead of building the whole app directly, developers first make a basic demo with simple screens like:  
Login page  
Menu page  
Order button  
You try it and say:  
“Add dark mode” or “change button position”.  
Developers update it and then make the final app.  
Shortly:  
Prototype Model = Build a sample → get feedback → improve → build final software.  

## Meaning of the Word Uncertain

Uncertain in Urdu means:  
ہونا نہ پکا / واضح غیر / یقینی غیر  
Simple meaning: When something is not sure or not confirmed.  
Example:  
“I am uncertain about the result.”  
→ ہے۔ نہیں یقین میں بارے کے رزلٹ مجھے  
→ Result pata nahi pakka kya hoga.  

## Scrum Master vs Project Manager

Scrum Master vs Project Manager (Simple Difference)  
Scrum Master:  
Helps the team follow Scrum rules  
Removes problems/obstacles for team  
Focus on team work and process  
Project Manager:  
Plans and controls the whole project  
Manages budget, time, and resources  
Focus on project success and delivery  
Short difference:  
Scrum Master = Team helper (process focus)  
Project Manager = Project controller (management focus)  

## Critical Path Method Step by Step

Critical Path Method (CPM) — Simple Full Explanation  
Critical Path Method (CPM) is a project management technique used to find:  
the minimum time needed to complete a project  
the most important tasks (critical tasks) that cannot be delayed  
where delay is allowed (slack/float)  
Key Idea  
A project has many tasks. Some tasks depend on others.  
CPM finds the longest path of dependent tasks = Critical Path  
If any task in this path is delayed → whole project is delayed  
Step-by-Step CPM Process  
We use 2 main calculations:  

### 1. Forward Pass → Earliest times

Find:  
ES (Early Start)  
EF (Early Finish)  

### 2. Backward Pass → Latest times

Find:  
LS (Late Start)  
LF (Late Finish)  
Example (Step by Step)  
Tasks:  
Task  
Duration  
Depends on  
B, C  
STEP 1: Forward Pass (ES, EF)  
Start from time 0  
Task A:  
ES = 0  
EF = 0 + 3 = 3  
Task B (after A):  
ES = 3  
EF = 3 + 2 = 5  
Task C (after A):  
ES = 3  
EF = 3 + 4 = 7  
Task D (after B & C):  
Take maximum EF of B and C = max(5, 7) = 7  
ES = 7  
EF = 7 + 2 = 9  
Project Duration = 9 units  
STEP 2: Backward Pass (LS, LF)  
Start from end = 9  
Task D:  
LF = 9  
LS = 9 - 2 = 7  
Task C:  
LF = LS of D = 7  
LS = 7 - 4 = 3  
Task B:  
LF = LS of D = 7  
LS = 7 - 2 = 5  
Task A:  
Take minimum LS of B and C = min(5, 3) = 3  
LF = 3  
LS = 3 - 3 = 0  
Final Table  
Task  
ES  
EF  
LS  
LF  
STEP 3: Find Critical Path  
Formula:  
If:  
ES = LS and EF = LF → task is critical  
So:  
A → yes (0=0, 3=3)  
B → NO  
C → YES  
D → YES  
Critical Path:  
A → C → D  
⏱ Project Duration:  
9 units  
Float / Slack (Important Case)  
Slack = LS - ES  
Task  
Slack  
Tasks with 0 slack = critical tasks  
Important Cases  

### 1. Multiple Critical Paths

Sometimes:  
more than one path has same longest duration  
Then project has multiple critical paths  

### 2. Zero Slack Case

If slack = 0:  
No delay allowed  

### 3. Positive Slack Case

If slack > 0:  
Task can be delayed without affecting project  

### 4. Merge Activity Case (very important)

When multiple tasks end into one:  
Always take:  
max EF (forward pass)  
min LS (backward pass)  
Intuition (Very Simple)  
Forward pass → “Earliest possible schedule”  
Backward pass → “Latest possible schedule without delay”  
Critical path → “tight chain of tasks”  
One-Line Summary  
CPM finds the longest dependent path in a project to determine the minimum completion time and critical  
tasks that cannot be delayed.  
a graph/network diagram version  
or a very hard exam-style CPM question with trick cases  
just tell me  

## What an Exam Question on CPM Gives

In exams, for Critical Path Method (CPM) questions, the teacher usually gives you a structured set of data  
so you can build the network and calculate forward/backward passes.  
Here’s what you typically get  

### 1. Activity List (Most common format)

You are given a table like this:  
Activity  
Duration  
Predecessor  
B, C  
This is the MOST IMPORTANT data in CPM questions.  

### 2. Sometimes: Activity-on-Arrow (AOA) diagram

Instead of a table, they give a network diagram showing:  
nodes (events)  
arrows (activities)  
durations on arrows  
You must directly do forward/backward pass on it.  

### 3. Sometimes: Activity-on-Node (AON)

each node = activity  
arrows = dependency  
Same idea, just different drawing style.  

### 4. Rare extra data (sometimes asked)

They may also give:  
⏱ Project start time  
usually assumed 0  
Calendar constraints  
like “start from day 1” or working days only  
Cost (in advanced CPM / crashing)  
normal cost  
crash cost  
used in cost-time tradeoff questions  
What YOU have to do in exam  
From given data, you must:  

### 1. Draw network diagram (if not given)

### 2. Do Forward Pass:

ES, EF  

### 3. Do Backward Pass:

LS, LF  

### 4. Find:

Slack  
Critical Path  
Project duration  
Important exam trick  
If multiple predecessors exist:  
always take maximum EF in forward pass  
If multiple successors exist:  
always take minimum LS in backward pass  
Simple Summary  
In exams, CPM questions mainly give you:  
Activities  
Durations  
Dependencies  
And you must calculate everything else yourself.  
marking.  

## Slack Time, ES, EF, LS, LF, Duration and Critical Path

Here are all CPM terms in a very simple and short way:  
⏱ 1. ES (Early Start)  
Earliest time a task can start  
After previous tasks finish  
⏱ 2. EF (Early Finish)  
Earliest time a task can finish  
Formula: EF = ES + Duration  
⏱ 3. LS (Late Start)  
Latest time a task can start without delaying project  
⏱ 4. LF (Late Finish)  
Latest time a task can finish without delaying project  
⏳ 5. Duration  
Time needed to complete a task  
(example: 3 days, 5 hours, etc.)  

### 6. Slack / Float

Extra time a task can be delayed without affecting project  
Formula:  
Slack = LS − ES (or LF − EF)  
Slack = 0 → no delay allowed  
Slack > 0 → delay allowed  

### 7. Critical Path

Longest path of dependent tasks  
It decides total project time  
Tasks on this path have zero slack  
If any delay happens → project delay  
Super Short Summary  
ES: start as early as possible  
EF: finish as early as possible  
LS: start as late as possible  
LF: finish as late as possible  
Duration: task time  
Slack: extra delay allowed  
Critical path: longest chain with zero slack  
1-minute exam trick to instantly find critical path and slack.  

## Formula for Slack Time

Exact formula for Slack (Float) time in CPM  
There are two correct formulas:  

### 1. Using Start times

### 2. Using Finish times

Slack = LS −ES  
Meaning (very simple)  
LS - ES → how much you can delay start  
LF - EF → how much you can delay finish  
Both give the same result  
Super simple example:  
If:  
ES = 2, LS = 5  
Slack = 5 − 2 = 3 units  
OR  
EF = 6, LF = 9  
Slack = 9 − 6 = 3 units  
Important exam note:  
If Slack = 0 → task is critical  
If Slack > 0 → task has flexibility  
diagram.  
Slack = LF −EF  
