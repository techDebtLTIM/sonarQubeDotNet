node {
  stage('SCM') {
    checkout scm
  } 
  stage('SonarQube Analysis') {
    def scannerHome = tool 'NewScanner'
    withSonarQubeEnv() {
      bat "dotnet ${scannerHome}\\SonarScanner.MSBuild.dll begin /k:\"SergioAVega_sonarQubeDotNet_AYuRTcoeMv0giqkxllET\""
      bat "dotnet build eShopOnWeb.sln"
      bat "dotnet ${scannerHome}\\SonarScanner.MSBuild.dll end"
    }
  }
}
