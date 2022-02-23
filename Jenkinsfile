node
{
stage('checkout')
    {
    checkout scm
    }

        stage('testing')
       {
        echo 'branch name ' + env.GIT_BRANCH
         if(env.GIT_BRANCH.startsWith("testing"))
             {
                 steps
                    {
                    sh 'echo "Working in testing branch"'
                     sh "mvn clean compile"
                     sh "mvn test"
                     }


             }
             }
          stage('devlopment')
          {

          if(env.GIT_BRANCH.startsWith("development"))
             {
                 steps
                     {
                     sh 'echo "Working in development branch"'
                     sh "mvn clean compile"
                     sh "mvn test"

                     }
             }
             }
             stage('production')
             {
         if(env.GIT_BRANCH.startsWith("Production"))
        {
          steps
          {
            sh 'echo "Working in Production branch"'
            sh "mvn clean compile"
            sh "mvn test"
            sh "mvn package"
            sh 'Deploying with Docker'



          }
        }
        }












    }



