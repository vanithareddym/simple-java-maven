podTemplate(yaml: '''
    apiVersion: v1
    kind: Pod
    spec:
      containers:
      - name: 'jnlp' 
        image: 'jenkins/inbound-agent:4.3-4'
        
    persistentVolumeClaim:
      mountPath: '/var/jenkins_home'
      claimName: 'jenkins-pv-claim'
      
    '''
)
 
{
    node(POD_LABEL) {
        stage('Build') { 
            
                sh '''
                    echo "Go Build"
                    '''
            
        }
    }
}    
