node('built-in')
{
    stage('conitnuousDownlod')
    {
    git 'https://github.com/IntelliqDevops/maven.git'
    }
    stage('conitnuousbuild')
    {
        sh 'mvn package'
    }
    stage('continuous-deployment')
    {
      deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '9d3c7be9-6fa8-442b-8168-ab2601e94b90', path: '', url: 'http://172.31.39.75:8080')], contextPath: 'test', war: '**/*.war'
    }
    stage('continuousTesting')
    {
        git 'https://github.com/kavali5096-pixel/testing.git'
        sh 'java -jar /var/lib/jenkins/workspace/scriptedpipeline4/testing.jar'
    }
    stage('continouos Delivery')
    {
        deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '9d3c7be9-6fa8-442b-8168-ab2601e94b90', path: '', url: 'http://172.31.44.40:8080')], contextPath: 'prodapp', war: '**/*.war'
    }
}
