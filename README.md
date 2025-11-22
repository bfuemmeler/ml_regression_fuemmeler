##  Machine Learning Final 
## C:\Repos\ml_regression_fuemmeler\notebook\regression_fuemmeler.ipynb
## Fuel Efficiency Regression Project

## Objective: 
This project applies machine learning techniques to predict vehicle fuel efficiency (mpg) based on engine specifications and vehicle attributes. Using the Auto MPG dataset, multiple regression models—including baseline linear regression, scaled pipeline regression, and polynomial regression—are evaluated and compared. The project demonstrates data cleaning, feature engineering, model training, and performance evaluation using R², MAE, and RMSE.

## Dataset

This project uses the Auto MPG dataset from the UCI Machine Learning Repository.  
Features include cylinders, displacement, horsepower, weight, acceleration, model year, and origin.  
The target variable is **fuel efficiency (mpg)**.

## About this Repository

Github repository for Module 6: Final Project on Regression Analysis:
https://github.com/bfuemmeler/ml_regression_fuemmeler

## Folders for Projects

Notebook folder containing the dataset and project file:
https://github.com/bfuemmeler/ml_regression_fuemmeler/tree/main/notebook

## Other Files to support this Project

.gitignore
https://github.com/bfuemmeler/ml_regression_fuemmeler/blob/main/.gitignore

Project Summary:
https://github.com/bfuemmeler/ml_regression_fuemmeler/blob/main/PROJECT_SUMMARY.md

Peer Review:
https://github.com/bfuemmeler/ml_regression_fuemmeler/blob/main/peer_review.md

README:
https://github.com/bfuemmeler/ml_regression_fuemmeler/blob/main/README.md


## How to Run the Notebook
1. Clone this repository  
2. Activate the project virtual environment  
3. Open VS Code  
4. Run the notebook located at: C:\Repos\ml_regression_fuemmeler\notebook\regression_fuemmeler.ipynb
   
## Model Results Summary

| Model | R² | MAE | RMSE |
|-------|--------|--------|--------|
| Baseline Linear Regression | 0.727 | 3.12 | 3.83 |
| Pipeline 1 (Scaled LR) | 0.727 | 3.12 | 3.83 |
| Pipeline 2 (Polynomial Deg=3) | **0.781** | **2.64** | **3.43** |

Polynomial Regression (degree 3) was the best-performing model.


## WORKFLOW 1. Set Up Machine

Proper setup is critical.
Complete each step in the following guide and verify carefully.

- [SET UP MACHINE](./SET_UP_MACHINE.md)


## WORKFLOW 2. Set Up Project

After verifying your machine is set up, set up a new Python project by copying this template.
Complete each step in the following guide.

- [SET UP PROJECT](./SET_UP_PROJECT.md)

It includes the critical commands to set up your local environment (and activate it):

```shell
uv venv
uv python pin 3.12
uv sync --extra dev --extra docs --upgrade
uv run pre-commit install
uv run python --version
```

**Windows (PowerShell):**

```shell
.\.venv\Scripts\activate
```

**macOS / Linux / WSL:**

```shell
source .venv/bin/activate
```


## WORKFLOW 3. Daily Workflow

Please ensure that the prior steps have been verified before continuing.
When working on a project, we open just that project in VS Code.

### 3.1 Git Pull from GitHub

Always start with `git pull` to check for any changes made to the GitHub repo.

```shell
git pull
```

### 3.2 Run Checks as You Work

This mirrors real work where we typically:

1. Update dependencies (for security and compatibility).
2. Clean unused cached packages to free space.
3. Use `git add .` to stage all changes.
4. Run ruff and fix minor issues.
5. Update pre-commit periodically.
6. Run pre-commit quality checks on all code files (**twice if needed**, the first pass may fix things).
7. Run tests.

In VS Code, open your repository, then open a terminal (Terminal / New Terminal) and run the following commands one at a time to check the code.

```shell
git pull
uv sync --extra dev --extra docs --upgrade
uv cache clean
git add .
uvx ruff check --fix
uvx pre-commit autoupdate
uv run pre-commit run --all-files
git add .
uv run pytest
```

NOTE: The second `git add .` ensures any automatic fixes made by Ruff or pre-commit are included before testing or committing.
Running `uv run pre-commit run --all-files` twice may be helpful if the first time doesn't pass. 

<details>
<summary>Click to see a note on best practices</summary>

`uvx` runs the latest version of a tool in an isolated cache, outside the virtual environment.
This keeps the project light and simple, but behavior can change when the tool updates.
For fully reproducible results, or when you need to use the local `.venv`, use `uv run` instead.

</details>

### 3.3 Build Project Documentation

Make sure you have current doc dependencies, then build your docs, fix any errors, and serve them locally to test.

```shell
uv run mkdocs build --strict
uv run mkdocs serve
```

- After running the serve command, the local URL of the docs will be provided. To open the site, press **CTRL and click** the provided link (at the same time) to view the documentation. On a Mac, use **CMD and click**.
- Press **CTRL c** (at the same time) to stop the hosting process.


### 3.4 How to Run the Project

1. Activate the virtual environment  
2. Open VS Code  
3. Open the notebook: notebook/regression_fuemmeler.ipynb
4. Run all cells (Shift+Enter)

## Update this README as you work

Add commands to run additional scripts as you work through the course (update the path and file name as needed).

---

### 3.5 Git add-commit-push to GitHub

Anytime we make working changes to code is a good time to git add-commit-push to GitHub.

1. Stage your changes with git add.
2. Commit your changes with a useful message in quotes.
3. Push your work to GitHub.

```shell
git add .
git commit -m "update README"
git push -u origin main
```

This will trigger the GitHub Actions workflow and publish your documentation via GitHub Pages.

### 3.6 Modify and Debug

With a working version safe in GitHub, start making changes to the code.

Before starting a new session, remember to do a `git pull` and keep your tools updated.

Each time forward progress is made, remember to git add-commit-push.
