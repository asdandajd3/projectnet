pipeline { 
    agent any 
    environment { 
        DOTNET_CLI_TELEMETRY_OPTOUT = '1' 
    } 
    stages { 
        stage('Checkout') { 
            steps { 
                git branch: 'main', url: 'https://github.com/asdandajd3/projectnet.git' 
            } 
        } 
        stage('Restore') { 
            steps { 
                bat 'dotnet restore' 
            } 
        } 
        stage('Build') { 
            steps { 
                bat 'dotnet build --no-restore' 
            } 
        } 
        stage('Publish') { 
            steps { 
                bat 'dotnet publish -c Release -o publish' 
            } 
        } 
    } 
    post { 
        success { echo '? Build th…nh c“ng!' } 
        failure { echo '? Build th?t b?i!' } 
    } 
} 
