pipeline{
agent any
tools {
maven 'Maven'
}
stages{
stage("Git Clone"){
steps
{
git 'https://github.com/PravinGuruputhiran007/hello-world.git'
}
}
stage("Build"){
steps
{
bat 'mvn clean install'
}
}
stage("Deploy"){
steps
{
bat 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipeline\\webapp\\target\\webapp.war C:\\Users\\Pravin\\Downloads\\apache-tomcat-10.0.27-windows-x64\\apache-tomcat-10.0.27\\webapps'
}
}
}
}
