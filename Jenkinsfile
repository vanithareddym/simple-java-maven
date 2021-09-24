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
    node(POD_LABEL)
    {
        stage('Get a Maven project') 
        {  
            git 'https://github.com/vanithareddym/simple-java-maven.git'
            
                stage('Build') 
                { 
                    steps 
                    {
                        sh 'mvn -B -DskipTests clean package' 
                    }  
                }
               
    
            
        }
    }
}    
