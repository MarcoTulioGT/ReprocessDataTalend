


/* Only keep the 10 most recent builds. */
def projectProperties = [
    [$class: 'BuildDiscarderProperty',strategy: [$class: 'LogRotator', numToKeepStr: '5']],
]
def imageName = 'jenkinsciinfra/jenkinsio'

 if (!env.CHANGE_ID) {
    if (env.BRANCH_NAME == null) {
        projectProperties.add(pipelineTriggers([cron('H/30 * * * *'), pollSCM('H/5 * * * *')]))
    }
}

properties(projectProperties)

pipeline {
    agent any
     environment {
    def branch = 'master'
    def pipelineName = 'Reproceso Jobs Talend'
	def file= 'Test_MQ'
    def workspace = pwd()
    def pass = ''
    //def emptyMap = [:]

}
    stages {
	stage('Seleccionar Job Talend') {
            steps {
                    script {	
                   echo 'Cambio Parametros'
				   }
        }
		}
        stage('Ejecutar Job'){
            steps{
               script{

            echo "Ejecutando Job"
            sh 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDIKfQ=='
               }
            }
        }
        stage('Validar Estatus Pipeline') {
            steps {
                    script {	
                   echo 'Desplegando Pipeline --> ' +pipelineName
             sh 'curl -X GET --header "Content-Type:application/json" http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogImdldFRhc2tTdGF0dXMiLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJ0YXNrSWQiOiA0Mgp9 '
			 }
            }
        }
	
    }
}
