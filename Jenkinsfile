////////////////////////////////////////////////////////////////////////////
//
// First things first - DO NOT use Jenkins editors (Blue Ocean) to edit this
// file. If you do, all the comments and formatting will be gone!!!
//
// Second, the actual pipeline definitions are all managed in the Tools
// repo, which must be registered as a shared library with the Jenkins
// master node - https://jenkins.io/doc/book/pipeline/shared-libraries/
//
////////////////////////////////////////////////////////////////////////////


// Load the shared library. The library must be defined on the master
// node in Manage Jenkins -> Configure System -> Global Pipeline Libraries.
// The definition associates a symbolic name with a Git repo and a branch.
// 
library "Library@master"

def createMap() {
	return [BUILD_TYPE: 'Native',
	        BRANCH_NAME: 'master',
	        ]
}

// Run the pipeline
//
if (env.JOB_NAME.endsWith('Call') ) {
	call (createMap ())
} else if (env.JOB_NAME.endsWith('Test') ) {
	test (createMap ())
