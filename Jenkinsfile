node
{
stage('checkout')
    {
    checkout scm
    }

        stage('test')
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
          stage('dev')
          {

          if(env.BRANCH_NAME.startsWith("development"))
             {
                 steps
                     {
                     sh 'echo "Working in testing branch"'
                     sh "mvn clean compile"
                     sh "mvn test"

                     }
             }
             }
             stage('prod')
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



