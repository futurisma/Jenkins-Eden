pipeline {

    agent any

    environment {
        BUILD_ENV = 'Dev'
        SELINUX = 'disabled'

    }

    stages {

        stage('Init_Node') {

            when {
                branch 'master'
            }

            steps {

                echo "\u2756 Init"
                echo " Node Url     :: ${env.NODE_IMG}"       // google/nodejs-hello
                echo " Node Ver     :: ${env.NODE_VER}"       // latest



            }
        }

        //  def pocImg = docker.build("${env.NODE_IMG}:${env.NODE_VER}", 'node')
        stage('Build-Node') {

            when {
                branch 'master'
            }

            steps {
                script {

                      def pocImg = docker.build("google/nodejs-hello:latest", 'node')
                       pocImg.tag('latest')

                  }
            }
      }


    }
}
