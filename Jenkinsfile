node ('agent') {
    stage ('Checks') {
        git url : https://github.com/NVB20/gradle-hello-world.git
    }
    stage ('Build') {
        //execute gradle build
        sh './build.gradle clean build'
    }
    stage ('Post') {

        if (!("SUCCESS".equals(currentBuild.previousBuild.result))) {
            //alt text 
            manager.addBadge("success.gif", "Success test")
        } else {
            manager.addBadge("warning.gif", "Warning test")                
        }      
    }
}
