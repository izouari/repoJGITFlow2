stage 'release'
node {
	echo "env.BRANCH_NAME : " env.BRANCH_NAME
    if(env.BRANCH_NAME == 'develop') {
        deleteDir()

        checkout scm

        git url: 'https://github.com/izouari/repoJGITFlow2.git', credentialsId: 'bea7e29c-dc87-42bc-97ab-2f258ca65ad6', branch: 'develop'

        def mvnHome = tool 'M2'

        sh "$mvnHome/bin/mvn clean jgitflow:release-start"
        sh "$mvnHome/bin/mvn clean jgitflow:release-finish -Dmaven.javadoc.skip=true"

        sh 'git checkout master'


    } else {
        echo "Current branch : "
        echo env.BRANCH_NAME
    }
}