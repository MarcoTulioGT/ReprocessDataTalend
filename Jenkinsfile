pipeline {
    agent any
	
	parameters{
	choice(name:'JOBSTALEND', choices:'customer_view\ncontract_information\ncustomer_view_vas_sale\ncustomer_view_dpi\ncustomer_view_by_pssprt', description:'Cual job de Talend deseas ejecutar?')
    //booleanParam(name:'CAN_DANCE', defaultValue: true, description: 'Checkbox parameter')
	//string(name: 'stpram', defaultValue: 'Dance!',  description: 'Do the Funky')
	}
	
	
     environment {
    def branch = 'master'
    def pipelineName = 'Reproceso Jobs Talend'
}
    stages {
        stage('Ejecutar Job'){
            steps{
               script{
                   if (params.JOBSTALEND != '') {
                         input message: 'Requiere Aprobación',
              parameters: [choice(name: 'Deploy Production', choices: 'NO\nSI', description: "Selecciona SI,  Si esta de acuerdo en ejecutar el Job ${params.JOBSTALEND} ")]
                 def r = 'Nada'
                  switch(params.JOBSTALEND) {
                  case "customer_view": 
                  echo "Ejecutando Job .... customer_view"  
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDIKfQ==', returnStdout: true)           
                  echo " El resultado es "+ r
                  break
                  case "contract_information": 
                  echo "Ejecutando Job .... contract_information" 
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogMzIxCn0=', returnStdout: true)                      
                  echo " El resultado es "+ r
                  break
                  case "customer_view_vas_sale": 
                  echo "Ejecutando Job .... customer_view"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDQxCn0=', returnStdout: true)                       
                  echo " El resultado es "+ r
                  break
                  case "customer_view_dpi": 
                  echo "Ejecutando Job .... customer_view_dpi"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNjAxCn0=', returnStdout: true)                      
                  echo " El resultado es "+ r
                  break
                  case "customer_view_by_pssprt": 
                  echo "Ejecutando Job .... customer_view_by_pssprt"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNjIxCn0=', returnStdout: true)                       
                  echo " El resultado es "+ r
                  break
              }
                   }
              }
            }
        }
        stage('Validar Estatus Pipeline') {
            steps {
                   script{
                 def r = 'Nada'
                  switch(params.JOBSTALEND) {
                  case "customer_view": 
                  echo "Ejecutando Job .... customer_view"  
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogImdldFRhc2tTdGF0dXMiLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJ0YXNrSWQiOiA0Mgp9', returnStdout: true)           
                  echo " El resultado es "+ r
                  break
                  case "contract_information": 
                  echo "Ejecutando Job .... contract_information" 
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogImdldFRhc2tTdGF0dXMiLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJ0YXNrSWQiOiAzMjEKfQ==', returnStdout: true)                      
                  echo " El resultado es "+ r
                  break
                  case "customer_view_vas_sale": 
                  echo "Ejecutando Job .... customer_view"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogImdldFRhc2tTdGF0dXMiLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJ0YXNrSWQiOiA0NDEKfQ==', returnStdout: true)                       
                  echo " El resultado es "+ r
                  break
                  case "customer_view_dpi": 
                  echo "Ejecutando Job .... customer_view_dpi"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogImdldFRhc2tTdGF0dXMiLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJ0YXNrSWQiOiA2MDEKfQ==', returnStdout: true)                      
                  echo " El resultado es "+ r
                  break
                  case "customer_view_by_pssprt": 
                  echo "Ejecutando Job .... customer_view_by_pssprt"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogImdldFRhc2tTdGF0dXMiLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJ0YXNrSWQiOiA2MjEKfQ==', returnStdout: true)                       
                  echo " El resultado es "+ r
                  break
              }
              }
            }
        }
		 stage('Revisar Monitoreo Kibana') {
            steps {
                    script {
				   echo "Ejecutando Job .... ${params.JOBSTALEND}"	


					  publishHTML target: [
            allowMissing: false,
            alwaysLinkToLastBuild: false,
            keepAll: true,
            reportDir: '',
            reportFiles: 'index.html',
            reportName: 'RCov Report'
          ]
		  
		  
                   
				   }
            }
        }
	
    }
}
