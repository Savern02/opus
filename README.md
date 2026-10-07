# opus
Auto Job filer in C++



Initial Thoughts:
Need a job queue + memory of jobs already applied so there is no double applying at same pos|compay unless specified 
Need scalability & parallelism - be able to run multiple "agents" for mass applying
Need to be able to review applications - A human needs to oversee the final filled out application before submission or fill out any questions that opus does not know
Need to work with multiple platforms - This will be abstracted to the web as application uses this so dynamic web crawler or UI + AI vision (cons and pros need to be weighed)
Need to be able to make accounts - Some companies require a account + application, either automate this process or get human help as SSO is not common and giving email access is annoying
Needs to store personal info + choices (remember questions and enter new ones) - for truly sensitive info no plain text, needs a rolling list of questions that will also update to the other running agents so we wont be stuck on the same question


C++(CLI, manger) and Python (AI vision, beautiful soup?, NLP?)

# High Level - User workflow
1. Give a list of jobs
2. Start dameon
3. Assign x amount of agents to work on jobs
4. The agent should open the link to the job app, determine if it needs a account or not (create one if so), then transverse the app and fill out all the necessary parts and prompt if needing help
5. Send to human to review, shut down
6. Once reviewed mark as complete and add to applied jobs database with date, company and position 
