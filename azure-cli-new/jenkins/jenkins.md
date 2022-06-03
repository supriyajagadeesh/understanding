* After installing jenkins, Creating Admin User
  ![preview](cicd/images/jenkins1.png)

* Jenkins setup
  ![preview](cicd/images/jenkins2.png)

* Adding user in master node 
  ![preview](cicd/images/jenkins3.png)

* Adding user in node 1
  ![preview](cicd/images/jenkins4.png)

* Installed java and maven in user "priya"
  ![preview](cicd/images/jenkins5.png)

* Ensuring java and git is installed or not
  ![preview](cicd/images/jenkins6.png)

* Launching Agent
  ![preview](cicd/images/jenkins7.png)

* Creating a Jenkins job to build spring petclinic for every hour in the Free style project 

  ![preview](cicd/images/jenkins8.png)

  ![preview](cicd/images/jenkins9.png)

  ![preview](cicd/images/jenkins10.png)

  ![preview](cicd/images/jenkins11.png)

  ![preview](cicd/images/jenkins12.png)


### Creating a Jenkins job to build spring petclinic for every hour by Scripted pipeline:

```
//Scripted Pipeline
node('build-jdk11-mvn3.8.5-1') {
    stage('git') 
    {git 'https://github.com/GitPracticeRepo/java11-examples.git'}
    stage('build') {
        sh '''
            echo "PATH=${PATH}"
            echo "M2_HOME=${M2_HOME}"

        '''
        sh '/usr/local/apache-maven-3.8.5/bin/mvn clean package'
    }
    stage('archive') {
        archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
    stage('publish test reports') {
        junit '**/TEST-*.xml'
    }
}
```
* Configuring required options
  ![preview](cicd/images/jenkins13.png)

  ![preview](cicd/images/jenkins14.png)
  
  ![preview](cicd/images/jenkins15.png)

* After setting up required parameters, clicking on build now
  ![preview](cicd/images/jenkins16.png)

* Pipeline steps
  ![preview](cicd/images/jenkins17.png)

  ![preview](cicd/images/jenkins18.png)

### Creating a Jenkins job to build spring petclinic for every hour by Declarative pipeline:

```

```
