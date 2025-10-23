# Composite actions defined.

### .github/actions/prepare-run/action.yml
    Generates prep.txt with a UUID and build number.
    Uploads it as prepData for other jobs.

### .github/actions/run-job/action.yml
    Pulls the prepData artifact.
    Runs the simulated job and creates a log.
    Uploads the log as <JobName>Data.

### .github/actions/integrate-jobs/action.yml
    Downloads logs for each job listed.
    Combines them into combined.txt.
    Uploads the result as integrationData.

### .github/actions/deploy/action.yml
    Downloads the combined results.
    Prints the results.

### .github/workflows/main.yml
    Clean, minimal workflow just like Jenkinsfile.
