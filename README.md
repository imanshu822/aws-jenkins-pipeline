### Testing the whole CI/CD pipeline

To test the whole solution, put an application on your GitHub repository.

The following screenshot shows an application tree containing the application source files, including text and binary files, executables, and packages:

![image](https://user-images.githubusercontent.com/48589838/89986084-a71ca200-dc99-11ea-9021-097d82084171.png)

In this example, the application files are the templates directory, test_app.py file, and web.py file.

The appspec.yml file is the main application specification file telling CodeDeploy how to deploy your application. Jenkins uses the AppSpec file to manage each deployment as a series of lifecycle event “hooks”, as defined in the file.

The buildspec.yml file is a collection of build commands and related settings, in YAML format, that CodeBuild uses to run a build. You can include a build spec as part of the source code, or you can define a build spec when you create a build project. For more information, see How AWS CodeBuild Works.

The scripts folder contains the scripts that you would like to run during the CodeDeploy LifecycleHooks execution with respect to your application requirements. For more information, see Plan a Revision for AWS CodeDeploy.

To test this solution, perform the following steps:

Unzip the application files and send them to your GitHub repository, run the following git commands from the path where you placed your sample application:

$ git add -A

$ git commit -m 'Your first application'

$ git push
On the Jenkins server dashboard, wait for two minutes until the previously set project trigger starts working. After the trigger starts working, you should see a new build taking place.

![image](https://user-images.githubusercontent.com/48589838/89986214-d92e0400-dc99-11ea-84cb-9ff3e830a1b8.png)

In the Jenkins server Console Output page, check the build events and review the steps performed by each Jenkins plugin. You can also review the CodeDeploy deployment in detail, as shown in the following screenshot:

![image](https://user-images.githubusercontent.com/48589838/89986227-dd5a2180-dc99-11ea-95a5-15938ac49df1.png)

On completion, Jenkins should report that you have successfully deployed a web application. You can also use your ELBDNSName value to confirm that the deployed application is running successfully.

![image](https://user-images.githubusercontent.com/48589838/89986033-9409d200-dc99-11ea-883c-37f6a469e02c.png)
