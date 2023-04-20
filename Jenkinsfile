/* Requires the Docker Pipeline plugin */
def params = []

pipeline {
    agent any
    stages {
        stage('Run Maven Tests') {
            steps {
                catchError {
                    sh '''
                        rm -rf testng-to-tm # name of your github repository
                        git clone https://github.com/harshbrowserstack/testng-to-tm # clone your github repository
                        cd testng-to-tm # cd to your repo
                        M2_HOME="/var/lib/jenkins/workspace/apache-maven-3.6.3/bin" # path to your maven
                        export PATH="$M2_HOME:$PATH" # set maven path if it does not exists
                        mvn clean # clean your maven project
                        mvn test # run your tests
                    '''
                }
            }
        }
    }
}
