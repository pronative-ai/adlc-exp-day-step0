# Instructions and Guidelines

## Prerequisites

* Repository: Fork this GitHub repository to get started.

* PronativeAI Environment Doctor: Install PronativeAI environemnt doctor (follow instructions from [https://www.npmjs.com/package/@pronative.ai/doctor](https://www.npmjs.com/package/@pronative.ai/doctor)).

* GitHub Auth token (Classic PAT): Generate a GitHub Personal Access Token (PAT) with 'repo', 'workflow', 'write:packages','delete:packages', 'project' scopes enabled. Copy & keep the token handy.

* Official Instructions to Generate a Classic PAT:
[https://docs.github.com/en/enterprise-server@3.18/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic](https://docs.github.com/en/enterprise-server@3.18/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic)

## User Setup Commands for GitHub Repo and Auth token

### Step 1: Configure your GitHub authentication token as a system environment variable:

**Linux / macOS:**

```bash
# For Zsh (Default on macOS)
echo 'export PRONATIVE_GH_TOKEN="your_personal_access_token_here"' >> ~/.zshrc

# For Bash
echo 'export PRONATIVE_GH_TOKEN="your_personal_access_token_here"' >> ~/.bashrc

```

**Windows PowerShell:**

```powershell
[Environment]::SetEnvironmentVariable("PRONATIVE_GH_TOKEN", "your_personal_access_token_here", "User")

```

### Step 2: Clone the forked repo locally and open it in VS Code:

```bash
git clone https://github.com/<your-github-username>/adlc-exp-day-step1.git
cd adlc-exp-day-step1
code .

```


## Triggering the AI Agent

### Step 1: Review or Customize the Requirements

If you want to modify the application business logic for your lab, you can open `DEVELOPMENT_INTENT.md` and customize certain sections. However, you must follow these strict guidelines:

* **What you CAN customize:** You are free to modify **Section 1 (Context and Business Goal)** to change the app idea, or adjust the fields and validation rules inside **Section 4 (Input / Output Functional Contracts)** to match your custom data requirements.
* **What you MUST leave AS IS:** Do **not** modify **Section 3 (Strict Boundary and Guardrails)**. The agent requires these exact rules to authenticate via your local environment variable and safely push your scaffolding/Pull Requests to GitHub.

### Step 2: Run the Agent

Open your OpenCode agent chat panel from VS Code Terminal, and paste below prompt to kick off the autonomous workflow:

```text
Act as an expert software engineer. Execute all phases of the specification sequentially from start to finish as metioned in 'DEVELOPMENT_INTENT.md' file. Perfoem a mandatory pre-flight verification check as mentioned in 'Pre-flight_Verification.md' file.

```
