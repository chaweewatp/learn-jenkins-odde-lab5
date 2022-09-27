pipeline {
    agent any
    environment { 
        drink = "Coffee"
    }
    parameters {
        choice(name: 'CHOICE', choices: ['Coffee', 'Tea'], description: 'What would you like to drink?')
    }
    stages {
        stage('Receiving order') {
            steps {

                echo "Choice: ${params.CHOICE}"
                script{
                    if(CHOICE == 'Tea'){
                        echo "you order tea"
                        // environment name: 'drink', value: "Tea"

                    } else{
                        echo "you order coffee"
                        // environment name: 'drink', value: "Coffee"
                    }
                    
                }
            }
        }
        // stage('order'){
        //     steps{
        //         echo "${drink}"
        //     }
        // }
        stage('ground coffee'){
            when {
                expression{ params.CHOICE == "Coffee"}
            }
            steps{
                echo "coffee1"
            }
        }
        stage('clean tea leaves'){
            when {
                expression{params.CHOICE == "Tea"}
            }
            steps{
                echo "tea1"
            }
        }
        stage('put in esspresso machine'){
            when {
                expression{params.CHOICE == "Coffee"}
            }
            steps{
                echo "coffee2"
            }
        }
        stage('put hot water'){
            when {
                expression{params.CHOICE == "Tea"}
            }
            steps{
                echo "tea2"
            }
        }
    }
    post { 
        always { 
            echo 'END job!'
        }
    }
}
