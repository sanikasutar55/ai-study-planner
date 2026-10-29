# Practical 7 – AI-Powered Student Study Planner

## Short explanation of the project
A single-page web app (HTML, CSS, JavaScript) where a student enters name, subject, topics, daily study hours, exam date and knowledge level. The app builds a prompt from these inputs, sends it to an AI model through an API, and receives a JSON study plan. The plan is rendered as priority cards, a day-wise timetable, a revision schedule, practice recommendations, level-specific tips and an exam strategy. Extra features: progress tracker, High/Medium/Low priority, revision date per topic, tips by level, and an AI quiz generator (5 MCQs + 5 short answers with answers, difficulty and explanations).

Flow: **Student Information → Prompt + API call → AI Processing → Personalized Study Plan**

## Step F – Answers
1. **How does GenAI generate the plan?** A language model predicts the most likely next tokens given the prompt. Having learned patterns of study schedules, it produces a plan that fits the inputs rather than looking up a stored one.
2. **Input to the AI:** name, subject, topics, hours/day, today's date, exam date, days left, knowledge level, the instruction (prompt) and the required JSON format.
3. **Role of the API:** It lets our app send the prompt to the model over HTTP and get the response back, so we don't run the model ourselves.
4. **Why an API key?** It identifies and authenticates the user, controls access, and tracks usage and billing.
5. **Role of OpenCode:** An AI coding agent in the terminal that wrote and modified the application code from natural-language prompts.
6. **Role of Codespaces:** A cloud development environment (VS Code + terminal) where OpenCode is installed and the app is built and run without local setup.
7. **How the prompt changes output:** A vague prompt gives a generic, short plan. Added structure (days, targets, revision) gives organized output. A role, goals and a request for reasoning gives deeper, justified, exam-focused output.
8. **Best prompt:** Prompt 3 (Advanced). It sets an expert role, asks for prioritization, balance of learning/practice/revision and explanations, so the plan is specific and justified. (Confirm this against your own runs.)
9. **Fewer study hours:** The AI shortens daily sessions, drops low-priority content, concentrates on high-priority and difficult topics, and compresses revision.
10. **Improvements:** user login and saved plans, calendar/reminder export, adaptive re-planning from progress, PDF export, backend to hide the API key, multi-subject support, mobile app (PWA/React Native), analytics from quiz scores.

## Step E – Prompt comparison (fill in with your real outputs)
| | Prompt 1 – Basic | Prompt 2 – Structured | Prompt 3 – Advanced |
|---|---|---|---|
| Detail | Low, generic | Medium, day-wise | High, topic-wise reasoning |
| Priorities explained | Rarely | Sometimes | Yes, with reasons |
| Revision/practice | Minimal | Included | Balanced and exam-focused |
| Best use | Quick idea | Clear schedule | Final personalized plan |

Prompts: (1) "Create a study plan for this student." (2) "Create a 15-day study plan and divide the topics into daily targets. Include revision and practice sessions." (3) "Act as an expert academic study planner…" (full text is in the app's prompt-style menu).

## Challenges faced
- Getting the AI to return valid JSON consistently
- Keeping the API key safe in a front-end app
- Making daily minutes fit the available hours
- CORS/API errors and model name selection
- Handling date calculations for the exam countdown

## Future improvements
Backend proxy for the key, login, saved history, calendar sync, notifications for revision dates, PDF export, mobile app, quiz-score-based adaptation.

## Viva answers
1. **Generative AI:** AI that creates new content (text, images, code) learned from data.
2. **API:** An interface that lets one program request services or data from another.
3. **API key:** A secret token that authenticates and bills requests.
4. **OpenCode:** An open-source AI coding agent that runs in the terminal.
5. **GitHub Codespaces:** A cloud-hosted developer environment on GitHub.
6. **Prompt engineering:** Designing inputs to get accurate, useful model outputs.
7. **Normal vs AI app:** A normal program follows fixed rules; an AI app generates varied, context-based output from a model.
8. **Prompt influence:** The model conditions on the prompt, so role, detail and format shape content and quality.
9. **Keep keys private:** Others could use them, causing cost, abuse and data exposure.
10. **To mobile:** Make it a PWA, wrap with Capacitor/Cordova, or rebuild in React Native/Flutter, and move the API call to a backend.

## Submission checklist
GitHub repo link · screenshots (app, OpenCode `/connect`, AI output) · source code · three prompts · comparison · explanation · challenges · improvements
