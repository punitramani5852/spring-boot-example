node
{
stage('checkout')
    {
    checkout scm
    }

        stage('testing')
       {
        echo 'branch name ' + env.BRANCH_NAME
         if(env.BRANCH_NAME.startsWith("testing"))
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

          if(env.BRANCH_NAME.startsWith("development"))
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
         if(env.BRANCH_NAME.startsWith("Production"))
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



