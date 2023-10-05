Calculator.js: a node.js Demonstration Project
==============================================
An example node.js project, including tests with mocha, that behaves like
a pocket calculator.

[![Build Status](https://dev.azure.com/lfcamargo/Integrating%20External%20Source%20Control%20with%20Azure%20Pipelines/_apis/build/status/lfcamargo1991.calculator?branchName=master)](https://dev.azure.com/lfcamargo/Integrating%20External%20Source%20Control%20with%20Azure%20Pipelines/_build/latest?definitionId=8&branchName=master)

The project contains a simple node.js application that exposes REST APIs
to perform arithmetic on integers, and provides a test suite with mocha
and chai.  The `mocha-junit-reporters` package is included to provide XML
output that can be presented in a continuous integration tool like
[Azure DevOps](https://azure.com/devops).

To build, simply:

1. Runs `npm install` to install dependencies.
2. Runs `npm test` to run Mocha and execute the unit tests.



================================================
GitRunner Windows x64
Configure
Download
We recommend configuring the runner under "\actions-runner". This will help avoid issues related to service identity folder permissions and long path restrictions on Windows.

# Create a folder under the drive root
$ mkdir actions-runner; cd actions-runner# Download the latest runner package
$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.309.0/actions-runner-win-x64-2.309.0.zip -OutFile actions-runner-win-x64-2.309.0.zip# Optional: Validate the hash
$ if((Get-FileHash -Path actions-runner-win-x64-2.309.0.zip -Algorithm SHA256).Hash.ToUpper() -ne 'cd1920154e365689130aa1f90258e0da47faecce547d0374475cdd2554dbf09a'.ToUpper()){ throw 'Computed checksum did not match' }# Extract the installer
$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-x64-2.309.0.zip", "$PWD")

# Create the runner and start the configuration experience
$ ./config.cmd --url https://github.com/lfcamargo1991/calculator --token ATFBPLKK7H3HEZDKBSRA4ITFDNVCC# Run it!  # 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
$ ./run.cmd
Using your self-hosted runner

# Use this YAML in your workflow file for each job 
runs-on: self-hosted