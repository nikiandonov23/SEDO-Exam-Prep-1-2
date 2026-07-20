pipeline {

    agent any

    stages {
        stage("Dotnet restore") {
            when {               // Ще се изпълнява само ако сме на main или feature branch               
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat 'dotnet restore' // Възстановяваме NuGet пакетите за проекта
            }
        }
        
        stage("Dotnet Build") { 
            when {            // Ще се изпълнява само ако сме на main или feature branch    
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        
        stage("Dotnet test") {
            when {  // Ще се изпълнява само ако сме на main или feature branch               
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {                
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
