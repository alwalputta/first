node ("master") {
    stage ("Init") {
        echo "Init ..."
        echo "Build ID: $BUILD_ID"
        echo "Job name: $JOB_NAME"
        echo "Branch name: $env.getEnvironment()"
        echo "Param name: $params.firstname"
        echo "Param name: ${params.lastname}"
        sh 'env > env.txt'
        readFile('env.txt').split("\r?\n").each {
            println it
        }
    }
    stage ("Build") {
        echo "Building ..."
     // Make the output directory.
        sh "mkdir -p output"
    // Write an useful file, which is needed to be archived.
        writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
    // Write an useless file, which is not needed to be archived.
        writeFile file: "output/uselessfile.md", text: "This file is useless, no need to archive it."
    }
    stage ("Test") {
        echo "Testing ..."
        if (currentBuild.result == 'SUCCESS') {
            sh 'make publish'
        }
    }
}
