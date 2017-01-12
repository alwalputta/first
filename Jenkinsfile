node ("master") {
    stage "SCM Checkout"
        echo "Checking out the code"
        echo "Branch name: $BUILD_ID"
        echo "Job name: $JOB_NAME"
        echo "Param name: $params.firstname"
        
    stage "Create Files"
        echo "Creating files"
     // Make the output directory.
        sh "mkdir -p output"
    // Write an useful file, which is needed to be archived.
        writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
    // Write an useless file, which is not needed to be archived.
        writeFile file: "output/uselessfile.md", text: "This file is useless, no need to archive it."
}
