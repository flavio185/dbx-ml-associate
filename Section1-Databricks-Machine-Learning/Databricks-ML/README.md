## 1 - Identify when a standard cluster is preferred over a single-node cluster and vice versa

####  When to Use Spark

● Scaling Out

    Data or model is too large to process on a single machine, commonly resulting in out-of-memory errors

● Speeding Up
    
    Data or model is processing slowly and could benefit from shorter processing times and faster results

Machine learning in Spark allows us to work with bigger data and train models faster by distributing the data and computations across multiple workers.

## 2 -  Connect a repo from an external Git provider to Databricks repos.

    To connect a repo from an external Git provider (such as GitHub or GitLab) to Databricks Repos, you can follow these steps:

    1. Open the Databricks workspace and navigate to the Repos tab.
    2. Click on the "Connect Repo" button.
    3. In the "Connect New Repo" dialog box, select the "Git Provider" option.
    4. Choose your preferred Git provider from the drop-down list.
    5. Select the appropriate authentication method based on your Git provider and repository configuration (SSH Key or Token).
    6. Enter the necessary details for authentication, such as the repository URL, authentication token, or SSH key.
    7. Click on the "Connect" button to connect the repo.

## 3 - Commit changes from a Databricks Repo to an external Git provider.

    To commit changes from a Databricks Repo to an external Git provider, you need to follow these steps:

    1- Make sure you have connected your Databricks Repo to the external Git provider. If not, refer to the previous response on how to connect a repo to Databricks Repos.

    2- Open the Databricks workspace and navigate to the Repos tab.

    3- Select the repo that you want to commit the changes to.

    4- Make the necessary changes to the files in the Databricks Repo. You can edit the files directly within the Databricks workspace or upload new files.

    5- Once you have made the changes, go back to the Repos tab.

    6- Click on the "Changes" tab within the repo. Here, you will see a list of all the modified files.

    7- Select the files that you want to commit by checking the checkboxes next to them.

    8- Add a commit message describing the changes you made in the "Commit Message" field.

    9 - Click on the "Commit" button to commit the changes to the Databricks Repo.

    10- Finally, go to your external Git provider (e.g., GitHub or GitLab) and sync/push the changes from the Databricks Repo to the repository on the external Git provider.

## 4 - Create a new branch and commit changes to an external Git provider.
    
    To create a new branch and commit changes to an external Git provider, follow these general steps:

    1. Clone the repository: First, clone the Git repository locally using the appropriate Git command. For example, if using Git command-line, you can use git clone <repository_url>.

    2. Change to the repository directory: Navigate to the cloned repository's directory using the cd command.

    3. Create a new branch: Use the git branch command to create a new branch. For example, to create a branch named "new-branch", you can use git branch new-branch.

    4. Switch to the new branch: Use the git checkout command to switch to the new branch. For example, to switch to the "new-branch", you can use git checkout new-branch.

    5. Make changes: Modify your files or add new files to your repository locally.

    6. Stage the changes: Use the git add command to stage the changes you want to commit. For example, to stage all changes, you can use git add ..

    7. Commit the changes: Use the git commit command to commit the staged changes. For example, you can use git commit -m "Commit message".

    8. Push the changes: Use the git push command to push the committed changes to the remote repository. For example, you can use git push origin new-branch to push the changes to the "new-branch" in the remote

## 5- Pull changes from an external Git provider back to a Databricks workspace.

    To pull changes from an external Git provider back to a Databricks workspace, follow these general steps:

    1- Make sure you have connected the Git provider repository to the Databricks workspace. If not, refer to the previous response on how to connect a repo to Databricks Repos.

    2- Open the Databricks workspace.

    3- Navigate to the Repos tab.

    4- Select the repo that you want to pull changes into.

    5- Click on the "Pull" button within the repo.

    6- Choose the appropriate branch to pull from the Git provider repository.

    7- Optionally, you can choose to preview the changes before pulling by enabling the "Preview Changes" toggle.

    8- Click on the "Pull Changes" button to pull the latest changes from the external Git provider repository.

## 6- Orchestrate multi-task ML workflows using Databricks jobs.

    To orchestrate multi-task ML workflows using Databricks jobs, you can follow these steps:

    1- Prepare your ML workflow: Identify the ML tasks that need to be performed and organize them sequentially in a workflow.

    2- Create a Databricks notebook: Create a Databricks notebook where you will define and execute your ML workflow. The notebook will contain the code and logic for the tasks in the workflow.

    3- Define the ML tasks: In the notebook, define each ML task as a separate code cell. Each task can include data preprocessing, training models, and evaluating results.

    4- Use Databricks job scheduler: Navigate to the Databricks workspace and go to the "Jobs" tab. Click on "Create Job" to create a new job.

    5- onfigure the job: Provide a name and description for the job. Specify the notebook containing the ML workflow. You can also configure the job to run on a schedule or with specific trigger events.

    6- Define job parameters: In the job configuration, define any necessary parameters that can be used to control the behavior of the ML workflow. This can include input data paths, model settings, or any other configurable aspects of the ML tasks.

    7- Sequence the ML tasks: In the notebook, ensure that the ML tasks are arranged in the desired sequence. You can use variable assignments, functions, or control flow statements to orchestrate the flow between the tasks.

    8- Execute the job: Submit the Databricks job to run the ML workflow. The job will trigger the execution of the notebook, which in turn executes the ML tasks in the specified sequence.

    9- Monitor the job: Monitor the progress and status of the Databricks job in the Databricks UI. You can track the execution of each task in the ML workflow and view the results.

    10- Iterate and refine: If needed, make adjustments to the ML workflow or job configuration, and re-run the Databricks job to execute the updated workflow.

    By following these steps, you can orchestrate multi-task ML workflows using Databricks jobs, allowing you to automate and schedule the execution of your ML pipelines.