# Quarto for university courses

A template for developing university courses using Quarto.

Real Examples:

- [LSE DS105](https://lse-dsi.github.io/DS105/) - Data for Data Science
- [LSE DS101](https://lse-dsi.github.io/DS101/) - Fundamentals of Data Science

**New to Quarto?**

You will need to understand the basics of the following features of Quarto to make the most of this template. It's worth it!

- Check [their initial tutorial](https://quarto.org/docs/get-started/)
- Then read about [Quarto websites](https://quarto.org/docs/websites/)
- Check out also [Revealjs tutorial](https://quarto.org/docs/presentations/revealjs/) to learn how to create modern slides
- Then move on to learn about [Quarto projects](https://quarto.org/docs/projects/quarto-projects.html)

There you go. You might be wondering how to put all of this to work. That is precisely why this template exists!

# How to use this template

**On GitHub:**

1. Click on the green button **Use this template** then **Create a new repository**.

2. Wait for GitHub to copy the files and run the initial setup (you will see this on the **Actions** tab).

**Locally in your computer:**

3. Clone your newly created repository to your computer.

4. Follow the instructions written below in the 🧰 [Dev Setup](#dev-setup) section.

5. Skip the R or Python setup if you do not plan on working in one of these languages.

6. Start editing the files! That is, identify the relevant files and remove the sections that refer to the template, leaving only what is relevant to developing/updating the material of your course.
    - Start by editing the `README.md` file carefully (you might want to change the title, remove some of the template sections, and edit the Dev Setup instructions to cater to your needs)
    - Then move on to `_quarto.yml`. What pages do you want to see on your website?


# 🧰 Dev Setup

On top of the setup below, I also recommend you use [VSCode](https://code.visualstudio.com/Download) as your primary IDE.

## 🐍 The Python setup

1. Install [Python 3.8](python.org) or higher on your computer.
2. Install [anaconda](https://www.anaconda.com/products/individual) or [miniconda](https://docs.conda.io/en/latest/miniconda.html) on your computer.
3. Create a new `conda` environment:

    ```bash
    conda create -y -n=venv-my-course python=3.10.8
    ```

    Never worked with conda environments before? Take some time to read [their documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html). 

    💡 **Pro-tip**: replace `my-course` with your course code. Say, for example, `venv-ds105`.

4. Activate the environment and make sure you have `pip` installed inside that environment:

  ```console
  # the exact `activate` command will vary depending on your OS
  conda activate venv-my-course 
  ```

💡 Remember to activate this particular `conda` environment whenever you reopen VSCode/the terminal.

10. Install required libraries

  ```console
  pip install -r requirements.txt
  ```

Now, whenever you open a Jupyter Notebook, you should see the `venv-my-course` kernel available.


## 📊 The R setup

1. Open a terminal and navigate to the root of this repository.
2. Ensure you have **R version 4.2.2** or higher
3. Open the R console in this same directory and install `renv` package:
    ```r
    install.packages("renv")
    ```
4. Run `renv::restore()` to install all the packages needed for this project
5. Whenever you install a new R package, run `renv::snapshot()` to save it on your renv.


## The Quarto setup

1. Install [Quarto](https://quarto.org/docs/getting-started/installation.html) on your computer.
2. Run the following command to start the website locally:

    ```bash
    quarto preview . --render all --no-browser
    ```
    This will read the instructions from `_quarto.yml` and render the website locally.
5. Open your browser and navigate to `http://localhost:<port>/`. That's it!

## Publishing the website

I recommend you set up a **GitHub Action** for this. Just follow the instructions in the official [Quarto instructions](https://quarto.org/docs/publishing/github-pages.html#publish-action).


