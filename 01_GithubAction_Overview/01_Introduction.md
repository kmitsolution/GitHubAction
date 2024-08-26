# GitHub Actions
<img src=https://github.com/user-attachments/assets/0d379e88-998f-442b-9795-e7eac09c167e width=100 height=50 />

Github Actions is a powerful automation tool integrated directly into GitHub. It allows you to automate tasks like building, testing, and deploying code whenever certain events happen in your GitHub repository (e.g., pushing code, creating a pull request).

### Key Components of GitHub Actions

1. **Workflow**:
   - A workflow is an automated process defined in a YAML file that lives in the `.github/workflows/` directory of your repository.
   - Workflows are triggered by specific events (like a push, pull request, or schedule).
   - Workflows can contain one or more jobs.

2. **Job**:
   - A job is a set of steps that run on the same runner (a virtual machine).
   - Jobs run in parallel by default, but you can configure dependencies so that jobs run sequentially.

3. **Step**:
   - A step is an individual task within a job. Steps can run commands, scripts, or even use pre-built actions from the GitHub Marketplace.
   - Each step runs in the same environment, so data can be shared between steps within a job.

4. **Runner**:
   - A runner is a server that runs your workflows when they're triggered. GitHub provides hosted runners, or you can use self-hosted runners.

5. **Events**:
   - Events are specific activities that trigger workflows. Common events include `push`, `pull_request`, and `schedule`.

6. **Actions**:
   - Actions are reusable commands or scripts that you can use in your workflows. They can be defined in your repository or used from the GitHub Marketplace.

### Example of a GitHub Actions Workflow

To manually trigger a GitHub Actions workflow, you can use the `workflow_dispatch` event. This allows you to run the workflow manually from the GitHub Actions tab in your repository.

Here's the modified workflow:

```yaml
# .github/workflows/hello-world.yml

name: Hello World

# Trigger this workflow manually
on: 
  workflow_dispatch:

jobs:
  say-hello:
    runs-on: ubuntu-latest  # The job will run on an Ubuntu runner

    steps:
    - name: Print Hello World
      run: echo "Hello, World!"  # Command to print Hello, World!
    - name: Print in Multi line
      run: |
         echo "Hello, Repo!"  # Command to print Hello, Repo!
         echo "Hello, Github" # Command to print Hello, Github
```

### Explanation

- **`on: workflow_dispatch`**: This event allows the workflow to be manually triggered via the GitHub UI.
- Everything else remains the same, with the job running on an Ubuntu runner and printing "Hello, World!" when the workflow is manually triggered.

### How to Trigger Manually

1. Go to the "Actions" tab in your GitHub repository.
2. Select the "Hello World" workflow from the list.
3. Click the "Run workflow" button to execute the workflow manually.

