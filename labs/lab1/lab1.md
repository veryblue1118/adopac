# Lab 1 - Introduction
In Lab 1 we are starting with an introduction into Pipelines-as-Code with Azure DevOps by building a first, basic Pipeline using the Azure DevOps Website. 

> Goto Azure DevOps, select your Organization and click on your previously created Project. If you have not create an Organization and a Project in Azure DevOps, please start with the preparation tasks in our [Before you start](labs/lab0/before-you-start.md) guide.

## 1.1 Create a YAML-Pipeline via GUI
Before we can start building our first pipeline, we need a Repository in Azure DevOps. 

> **What is Azure Repos?** <br> Azure Repos is a set of version control tools that you can use to manage your code. Whether your software project is large or small, using version control as soon as possible is a good idea. <br>Version control systems are software that help you track changes you make in your code over time. As you edit your code, you tell the version control system to take a snapshot of your files. The version control system saves that snapshot permanently so you can recall it later if you need it. Use version control to save your work and coordinate code changes across your team.<br>Goto [docs.microsoft.com](https://docs.microsoft.com/azure/devops/repos/get-started/what-is-repos?view=azure-devops) to learn more.

To initialize the default repository we have in our DevOps Project, click on **Repos** -> **Files** and select **Import a repository**.

![Repos and Files](img/lab1_repos_files.png)

![Import Repository](img/lab1_import_repo.png)

Here we're now importing the Lab Repository from GitHub:

![Import a Git repository](img/lab1_import_a_git_repository.png)

**Settings:**
* Repository type: Git
* Clone URL: https://github.com/heoelri/adopac.git

And click on "Import".

This will now import the whole Repository from GitHub into your new Azure DevOps Repository.

* Click on "Pipelines"
* Click on "Pipelines"
* Click on "Create Pipeline"

In the "Where is your code?" section:

* Click "Azure Repos Git (YAML)

In the "Select a repository" section:

* Select "MyDevOpsProject" (or the name you selected for your DevOps project)

In the "Configure your pipeline" section:

* Select "Starter pipeline" 

This will now create a new basic YAML-based pipeline for you.

![Review your pipeline](img/lab1_review_your_pipeline.png)

## 1.2 Run your pipeline

Now that we have created our very first "Starter pipeline"

* Click "Save and run"

to save the pipeline in your repository and run it. "Save and run" will ask you for a "Commit message" to describe your change in your repository:

![Save and Run](img/lab1_save_and_run.png)

Select the following options:

* Commit message: <your commit message>
* Optional extended description: <additional description>
* Commit directly to the master branch

And click on:

* Save and run

You can also select if you want to write your change into the master branch or if you want to create another branch for your change.

The pipeline will now start and after a few seconds the output should look like this:

![Pipeline Output](img/lab1_pipeline_output.png)

This is the summary of a specific pipeline run. You can come back at any time to lookup the status and the output of a specific pipeline run.

> **What is a Branch?**<br>
> Branches are lightweight references that keep a history of commits and provide a way to isolate changes for a feature or a bug fix from your master branch and other work. Committing changes to a branch doesn't affect other branches. You can push and share branches with other people on your team without having to merge the changes into master.<br>
> To learn more about branches, goto [docs.microsoft.com](https://docs.microsoft.com/azure/devops/repos/get-started/key-concepts-repos?view=azure-devops#branch).

## 1.3 Analyze the output
The previously created pipeline was very basic. It does not contain much more than a one-line script that prints out "Hello World" and a multi-line script that prints out two lines with very basic echo commands.

Let us now have a deeper look into the output of your pipeline.

* Click on "Pipelines" > "Pipelines"
* Click on your pipeline in "Recently run pipelines"

![Recently run pipelines](img/lab1_recently_run_pipelines.png)

In this dialog you'll now see all runs of your selected pipeline. 

* Select the last pipeline run

Here you'll now see the details of the last pipeline run:

![Last pipeline run with comments](img/lab1_last_pipeline_run_with_comments.png)

This dialog shows you some important information, like:

1) Who has triggered the pipeline
2) The branch (here master)
3) Start date/time
4) Duration
5) Jobs and their status

To get even more insights about the jobs, 

* click on "Job" 

in the "Jobs" section. This will bring you to the job details:

![Pipeline Output](img/lab1_job_output.png)

Here you can now get deeper insights into each indiviual job and their tasks and steps.

* Click on "Run a one-line script"

![Job Status Output](img/lab1_job_status_one_line_script.png)

## 1.4 Use the assistant to add tasks
Now that we've a better understanding of where to find what, we're going to extend our pipeline a bit.

* Click "Pipelines" > "Pipelines"
* Select your "Pipeline"
* Click on "Edit" (top right)

This will bring us back to the pipeline editor we've seen before.

To get a better understanding of how to work with tasks and how to extend your pipeline, we're now going to add a third "bash" task to our pipeline.

* Search in the "Tasks" section for "bash"

![Tasks - Search for Bash](img/lab1_tasks_search_for_bash.png)

* Click on "Bash"
* Select Type "Inline"
* Modify the "Script" section with an individual comment

![Bash Task](img/lab1_bash_task_greetings.png)

* Click on "Add"

We can now see that there was a new section added to our YAML pipeline:

![New Section in Pipeline](img/lab1_new_bash_task_in_editor.png)

* Click on "Save" (top right) to save your changes

We again see that you can now specify a "Commit message" and an optional "extended description". Leave everything as is and "Commit directly to the master branch".

* Click "Save"

Our changes were now saved into our Repository (master branch) and you can now

* Click "Run" (top right) to run the modified pipeline

![Run pipeline](img/lab1_run_pipeline.png)

* Select the "master" branch and click "Run"

You can now (as learned in Lab 1.3) have a deeper look into the job output to make sure that our new bash task works as expected:

![Bash task](img/lab1_bash_task.png)

![Bash task output](img/lab1_bash_task_output.png)

## 1.5 Extend your pipeline with variables

## 1.6 Check the pipeline within your repository