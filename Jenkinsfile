node('codebuild') {
    ansiColor('xterm') {
        def initialCommit = 'f39f95ca0'
        def velocityTeamDevChannelWebhook = "https://outlook.office.com/webhook/162434eb-cd28-4a23-9e0c-500cfe92147f@189de737-c93a-4f5a-8b68-6f4ca9941912/JenkinsCI/ded78de239054e91bc354511e48ad65b/ce25d3e0-bec6-4ef3-83c7-1ee9344ea26e"
        def gitBranch
        def currentCommit
        def committer
        def userEmail
        def changeId
        def sinceCommitHash
        def lastSuccessfulCommitHash
        def sourceVersion
        def commitMessage
        def isMasterBuild
        def isReleaseBuild
        def isPr
        def velocityVersion
        def artifactPathOverride
         stage('Prep') {
            /* pull down source code */
            def scmVars = checkout scm
            currentCommit = scmVars.GIT_COMMIT
            step([
                $class: 'UploadBuild',
                debug: true,
                fatal: false,
                id: "${currentBuild.displayName}",
                name: "${currentBuild.displayName}",
                appName: 'UCV',
                startTime: "${currentBuild.startTimeInMillis}",
                endTime: "${System.currentTimeMillis()}",
                requestor: "test",
                revision: "${currentCommit}",
                status: "${status}",
                tenantId: "5ade13625558f2c6688d15ce",
                versionName: "${currentBuild.displayName}"
            ])
        }
    }
}
