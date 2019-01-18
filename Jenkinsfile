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
                 def r = 'Nada'
                  switch(params.JOBSTALEND) {
                  case "customer_view": 
                  echo "Ejecutando Job .... customer_view"  
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDIKfQ==', returnStdout: true)           
                  echo " El resultado es "+ r
                  break
                  case "contract_information": 
                  echo "Ejecutando Job .... contract_information" 
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDIKfQ==', returnStdout: true)                      
                  echo " El resultado es "+ r
                  break
                  case "customer_view_vas_sale": 
                  echo "Ejecutando Job .... customer_view"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDIKfQ==', returnStdout: true)                       
                  echo " El resultado es "+ r
                  break
                  case "customer_view_dpi": 
                  echo "Ejecutando Job .... customer_view_dpi"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDIKfQ==', returnStdout: true)                      
                  echo " El resultado es "+ r
                  break
                  case "customer_view_by_pssprt": 
                  echo "Ejecutando Job .... customer_view_by_pssprt"
                  r = sh( script: 'curl -X GET --header "Content-Type:application/json"  http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogInRhc2tMb2ciLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJsYXN0RXhlY3V0aW9uIjogdHJ1ZSwKICAidGFza0lkIjogNDIKfQ==', returnStdout: true)                       
                  echo " El resultado es "+ r
                  break
              }
              }
            }
        }
        stage('Validar Estatus Pipeline') {
            steps {
                    script {	
                   echo "Ejecutando Job .... ${params.JOBSTALEND}"
             sh 'curl -X GET --header "Content-Type:application/json" http://172.22.37.21:8080/tac/metaServlet?ewogICJhY3Rpb25OYW1lIjogImdldFRhc2tTdGF0dXMiLAogICJhdXRoUGFzcyI6ICJUaWdvLjIwMTghIiwKICAiYXV0aFVzZXIiOiAiZHdoX2RndGxAdGlnby5jb20uZ3QiLAogICJ0YXNrSWQiOiA0Mgp9 '
			 }
            }
        }
		 stage('Revisar Monitoreo Kibana') {
            steps {
                    script {
				   echo "Ejecutando Job .... ${params.JOBSTALEND}"					
                   echo "http://172.22.49.29:5601/app/kibana#/dashboard/e1996d20-d6ea-11e8-be3c-1f2fb3696472?_g=(refreshInterval:(display:'1%20minute',pause:!f,section:2,value:60000),time:(from:now-12h,mode:quick,to:now))&_a=(description:'',filters:!(),fullScreenMode:!f,options:(darkTheme:!t,hidePanelTitles:!f,useMargins:!t),panels:!((embeddableConfig:(),gridData:(h:16,i:'15',w:48,x:0,y:85),id:'45d6efd0-0303-11e9-994b-bb4a3c9fc393',panelIndex:'15',type:visualization,version:'6.3.1'),(embeddableConfig:(),gridData:(h:11,i:'18',w:22,x:0,y:0),id:'4549b810-1909-11e9-994b-bb4a3c9fc393',panelIndex:'18',type:visualization,version:'6.3.1'),(embeddableConfig:(),gridData:(h:11,i:'19',w:26,x:22,y:0),id:'3c624a80-190b-11e9-994b-bb4a3c9fc393',panelIndex:'19',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:(READY_TO_RUN:%230A50A1,RUNNING:%23E24D42))),gridData:(h:6,i:'20',w:48,x:0,y:39),id:'100a4790-19cd-11e9-994b-bb4a3c9fc393',panelIndex:'20',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:(READY_TO_RUN:%230A437C,RUNNING:%23E24D42),legendOpen:!t)),gridData:(h:6,i:'21',w:48,x:0,y:33),id:'2b5c3d90-19d3-11e9-994b-bb4a3c9fc393',panelIndex:'21',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:(READY_TO_RUN:%230A437C,RUNNING:%23E24D42))),gridData:(h:6,i:'22',w:48,x:0,y:45),id:'06ccd880-19d4-11e9-994b-bb4a3c9fc393',panelIndex:'22',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:(READY_TO_RUN:%230A437C,RUNNING:%23E24D42))),gridData:(h:6,i:'23',w:48,x:0,y:51),id:bf0ef360-19d4-11e9-994b-bb4a3c9fc393,panelIndex:'23',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:(READY_TO_RUN:%230A437C,RUNNING:%23E24D42))),gridData:(h:6,i:'24',w:48,x:0,y:57),id:e9b6c020-19d4-11e9-994b-bb4a3c9fc393,panelIndex:'24',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:('bytes%20read':%23C15C17))),gridData:(h:11,i:'25',w:22,x:0,y:11),id:'9fed56c0-19d9-11e9-994b-bb4a3c9fc393',panelIndex:'25',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:('bytes%20read':%237EB26D))),gridData:(h:11,i:'26',w:26,x:22,y:22),id:e9d0f020-19da-11e9-994b-bb4a3c9fc393,panelIndex:'26',type:visualization,version:'6.3.1'),(embeddableConfig:(vis:(colors:('bytes%20read':%23614D93))),gridData:(h:11,i:'27',w:22,x:0,y:22),id:c5923130-19dd-11e9-994b-bb4a3c9fc393,panelIndex:'27',type:visualization,version:'6.3.1'),(embeddableConfig:(),gridData:(h:11,i:'28',w:26,x:22,y:11),id:'5c9152e0-19df-11e9-994b-bb4a3c9fc393',panelIndex:'28',type:visualization,version:'6.3.1'),(embeddableConfig:(),gridData:(h:11,i:'30',w:24,x:24,y:63),id:a56464d0-1a1b-11e9-994b-bb4a3c9fc393,panelIndex:'30',type:visualization,version:'6.3.1'),(embeddableConfig:(),gridData:(h:11,i:'31',w:24,x:0,y:74),id:'1f842b00-1a1d-11e9-994b-bb4a3c9fc393',panelIndex:'31',type:visualization,version:'6.3.1'),(embeddableConfig:(),gridData:(h:11,i:'32',w:24,x:0,y:63),id:'6fb90bd0-1a1e-11e9-994b-bb4a3c9fc393',panelIndex:'32',type:visualization,version:'6.3.1')),query:(language:lucene,query:''),timeRestore:!t,title:'SSIT%20DataEcosystem',viewMode:view)"
				   }
            }
        }
	
    }
}
