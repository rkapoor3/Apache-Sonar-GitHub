# Apache SonarQube and GitHub Projects

This project includes how to download projects from GitHub using the Git Bash and then, analyzing the code quality using the SonarQube

Steps to follow:

1. Downloading projects from GitHub

-- Projects can be downloaded based on users or an organization. 
-- Open Git Bash and run the following command:
curl "https://api.github.com/users/pazdera/repos?per_page=100" | grep -e 'git_url*' | cut -d \" -f 4 | xargs -L1 git clone

2. Setting up SonarQube

-- Download SonarQube from the following link:
   https://www.sonarqube.org/downloads/

-- Then, Start the SonarQube server and check if its working fine by following the steps on 
   https://docs.sonarqube.org/display/SONAR/Get+Started+in+Two+Minutes

3. Download Apache Maven ( To scan Maven projects)

-- Download apache maven (binary zip archive) from https://maven.apache.org/download.cgi and set up the environment variables 
as mentioned in https://maven.apache.org/install.html.

-- Once the path is set, run mvn command on the command prompt to check if maven is installed properly.

4. Make sure you have a Maven project downloaded on your machine. An example of a Maven project which can be used for this purpose 
can be found on https://github.com/SonarSource/sonar-scanning-examples/tree/master/sonarqube-scanner-maven

5.	Now, change directory to the project’s directory and run the following command:

mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=0a79ae8375ac11f1e756d2a9fc4a51b255978b23

Note: 0a79ae8375ac11f1e756d2a9fc4a51b255978b23 is an auto-generated token for my login. You can generate this token when you login 
to http://localhost:9000 after you download the SonarQube.
After the above command, login to http://localhost:9000/projects and you will be able to see your project there. 


