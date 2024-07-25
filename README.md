# Quarto template for university courses

<figure>
    <img src="./figures/icons/course_favicon.png" alt="Image Created with DALL·E. Prompt: 'octopus-like alien futuristic teacher, abstract award-winning material design favicon blue flat colours'"  role="presentation" style="object-fit: cover;width:5em;height:5em;border-radius: 50%;">
    <figcaption>
        <span style="display:inline-block;font-size:0.3em;width:30%;">
        Image created with DALL·E. Prompt: 'octopus-like alien futuristic teacher, abstract award-winning material design favicon blue flat colours'
        </span>
    </figcaption>

</figure>


A template for developing university courses using Quarto.

**Real Examples:**

- <img src="https://lse-dsi.github.io/DS101/figures/DS101_favicon.png" style="object-fit: cover;width:1em;height:1em;border-radius: 50%;" /> [LSE DS101](https://lse-dsi.github.io/DS101/) - Fundamentals of Data Science
- <img src="https://lse-dsi.github.io/DS105/figures/icons/DS105L_favicon.png" style="object-fit: cover;width:1em;height:1em;border-radius: 50%;" /> [LSE DS105](https://lse-dsi.github.io/DS105/) - Data for Data Science
- <img src="https://lse-dsi.github.io/DS202/figures/icons/favicon_DS202_200px.png" style="object-fit: cover;width:1em;height:1em;border-radius: 50%;" /> [LSE DS202](https://lse-dsi.github.io/DS202/) - Data Science for Social Scientists
- <img src="https://lse-dsi.github.io/ME204/figures/icons/favicon_ME204_200px.png" style="object-fit: cover;width:1em;height:1em;border-radius: 50%;" /> [LSE ME204](https://lse-dsi.github.io/ME204/) - Data Engineering for the Social World

**New to <img src="https://quarto.org/favicon.png" style="object-fit: cover;width:1em;height:1em;" /> Quarto?**

You will need to understand the basics of the following features of Quarto to make the most of this template. It's worth it!

- Check [their initial tutorial](https://quarto.org/docs/get-started/)
- Then read about [Quarto websites](https://quarto.org/docs/websites/)
- Check out also [Revealjs tutorial](https://quarto.org/docs/presentations/revealjs/) to learn how to create modern slides
- Then move on to learn about [Quarto projects](https://quarto.org/docs/projects/quarto-projects.html)

There you go. You might be wondering how to put all of this to work. That is precisely why this template exists!

# 💡 How to use this template

<details><summary><strong>On GitHub:</strong></summary>

1. Click on the green button **Use this template** then **Create a new repository**.

2. Wait for GitHub to copy the files and run the initial setup (you will see this on the **Actions** tab).
</details>

<details><summary><strong>Locally in your computer:</strong></summary>

3. Clone your newly created repository to your computer.

4. Follow the instructions written below in the 🧰 [Dev Setup](#dev-setup) section.

5. Skip the R or Python setup if you do not plan on working in one of these languages.

</details>

<details><summary><strong>Start editing the files:</strong></summary>

Here is a guide of the initial files you might want to modify to remove the sections that refer to the template, leaving only what is relevant to developing/updating the material of your course.

6. Start by editing the `README.md` file carefully. 
    - Change the title
    - Remove some of the sections
    - Edit the Dev Setup instructions to cater to your needs.
7. Add your **course code** and **course name** to the web pages

    - If you are using VSCode, you can Ctrl + Shift + F (or ⌘ + Shift + F if you are on Mac) and replace all occurrences of `MY_COURSE_CODE` and `MY_COURSE_NAME` to the code and name of your course, respectively.
    - Or, you can manually edit those in the following files:
        - `_quarto.yml`
        - `2023/index.qmd`
        - `helpers/remove-nav.html`

8. Then move on to `_quarto.yml`. Scan through this file to spot what you want to change. What pages do you want to keep or remove from your website?

9. Next, modify the content of `index.qmd` and start working properly on your content pages under `2023/*`

10. Visualise your changes by running the Quarto website locally:

    ```bash
    quarto preview . --render all --no-browser
    ```
</details>

# 🧰 Dev Setup

On top of the setup below, I also recommend you use [VSCode](https://code.visualstudio.com/Download) as your primary IDE.

<details><summary>🐍 The Python setup</summary>

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

    ```bash
    # the exact `activate` command will vary depending on your OS
    conda activate venv-my-course 
    ```

💡 Remember to activate this particular `conda` environment whenever you reopen VSCode/the terminal.

10. Install required libraries

  ```bash
  pip install -r requirements.txt
  ```

Now, whenever you open a Jupyter Notebook, you should see the `venv-my-course` kernel available.
</details>

<details><summary>📊 The R setup</summary>

## 📊 The R setup

1. Open a terminal and navigate to the root of this repository.
2. Ensure you have **R version 4.2.2** or higher
3. Open the R console in this same directory and install `renv` package:
    ```r
    install.packages("renv")
    ```
4. Run `renv::restore()` to install all the packages needed for this project
5. Whenever you install a new R package, run `renv::snapshot()` to save it on your renv.

</details>

<details><summary><img src="https://quarto.org/favicon.png" style="object-fit: cover;width:1em;height:1em;" /> The Quarto setup</summary>

## <img src="https://quarto.org/favicon.png" style="object-fit: cover;width:1em;height:1em;" /> The Quarto setup

1. Install [Quarto](https://quarto.org/docs/getting-started/installation.html) on your computer.
2. Run the following command to start the website locally:

    ```bash
    quarto preview . --render all --no-browser
    ```
    This will read the instructions from `_quarto.yml` and render the website locally.
5. Open your browser and navigate to `http://localhost:<port>/`. That's it!

</details>

<details><summary>🕸️ Publishing the website</summary>

## 🕸️ Publishing the website

I recommend you set up a **GitHub Action** for this. Just follow the instructions in the official [Quarto instructions](https://quarto.org/docs/publishing/github-pages.html#publish-action).

💡 This template already comes with a GitHub workflow setup. You can find it in the [.github/workflows/publish.yml_](.github/workflows/publish.yml_) file. You just need to rename it to `.github/workflows/publish.yml` (remove the underscore at the end)

</details>

# 📟 Contact

**✋ Questions? Suggestions?** If you are not sure how to do something with the template or have a suggestion for a new feature, start a [discussion](https://github.com/jonjoncardoso/quarto-template-for-university-courses/discussions).

**🐞 Spotted any bugs?** Create a new [Issue](https://github.com/jonjoncardoso/quarto-template-for-university-courses/issues).

**🖼️ Want to show us your courses?** Share a link to your public page on the [discussions page](https://github.com/jonjoncardoso/quarto-template-for-university-courses/discussions) or write me an e-mail.