# GitHub Learnings
**Understanding the Github actions**

Before that lets understand the Continuous Integration (CI) and Continuous Deployment (CD).
- CI is nothing allowing multiple contributors or developers to merge the code they developed and ensuring the correctness by avoid the code merge conflicts, build(s) quality and automate testing by allowing to run tests during the merge cycles.
- CD is about moving the published/package code into the servers by automating the code build from the repository and moving the artefacts into the target server/services/cloud offerings/environments.

**GitHub Actions** are resuable pieces of code, which helps perform certain tasks like checkout the code from repository, build in a virtual environments and push the build artefacts into the targeted environments. We do have a lot other tasks/actions and integrations, which will help the developer communication to improve the productivity and collaborate effectively. Let deep dive into Githib actions workflow and runners as we progress.

- Github actions workflows triggers can run on Schedule, Invoke manually, by external events or internal github events itself. Some of them will be like code push, pull request, wiki page etc. Workflows run in virtual machines these are called as Runners, they are preconfigured VM machines, we can have Windows, Linux or MacOS. We do have provision for selfhosted runners, which can from any cloud providers or any onpremise machine too.
- Every workflow can have a name and the trigger, which is followed by Jobs. Each job can have a name and certain steps in it, each job runs on certain virtual environment. Normally all the jobs run parallely, subsequent jobs can depend on other jobs which can be enforced by using the job names. Each job will have steps and even step can be a action or command to run on runners.
- We will be writting all the above mentioned steps in YAML language (Yet Another Markup Language)
  ![image](https://github.com/aspire2buildinyourway/githublearnings/assets/135804475/e6cbc861-9f67-44cd-80e4-76eea26a6528)

 **Workflow triggers and Variables** 
  - Schedule Trigger using the cron expression(* * * * *)  explore CronGuru.
  - Over API using github api's.
  - Context variables and Environment variables (${{variablename}})
  - Expressions, Conditions and Functions (startswith, always(), failure(), success() etc)
  - Using scripts in the workflow (run: | next line write all the scripts)
  
    **Types of Github Actions**
    - Javascript Actions
    - Docker Actions
    - Composite Actions

    **Sharing data between Jobs**
    - Job Output variables simple strings can be passed
    - Uploading and downloading as artefacts using the github actions
    - Using Cache route (5gb cache per limit)