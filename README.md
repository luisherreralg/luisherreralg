<div id="header" align="center">
  <img src="https://media.giphy.com/media/M9gbBd9nbDrOTu1Mqx/giphy.gif" width="100"/>
</div>

<div id="badges" align='center'>
  <a href="https://www.linkedin.com/in/lherreralg/">
    <img src="https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge"/>
  </a>
</div>
<div id='viewsCounter' align='center'>
  <img src="https://komarev.com/ghpvc/?username=luisherreralg&style=flat-square&color=blue" alt=""/>
</div>
<h1>
  hey there
  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="30px"/>
</h1>
<div align="center">
  <img src="https://media.giphy.com/media/dWesBcTLavkZuG35MI/giphy.gif" width="600" height="300"/>
</div>

---

### :man_technologist: About Me :
I am a Full Stack Developer <img src="https://media.giphy.com/media/WUlplcMpOCEmTGBtBW/giphy.gif" width="30"> from Spain.
- :telescope: I’m working as a Software Engineer and contributing to frontend and backend for building web applications.

- :seedling: Exploring Technical Content Writing.

- :zap: In my free time, I solve problems on GeeksforGeeks and read tech articles.

- :mailbox:How to reach me: [![Linkedin Badge](https://img.shields.io/badge/-lherreralg-blue?style=flat&logo=Linkedin&logoColor=white)](https://www.linkedin.com/in/lherreralg/)

---
### :hammer_and_wrench: Languages and Tools :
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original-wordmark.svg" title="React" alt="React" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/css3/css3-plain-wordmark.svg"  title="CSS3" alt="CSS" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-original.svg" title="HTML5" alt="HTML" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" title="JavaScript" alt="JavaScript" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/nodejs/nodejs-original-wordmark.svg" title="NodeJS" alt="NodeJS" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-original-wordmark.svg" title="Git" **alt="Git" width="40" height="40"/>
    <img src="https://github.com/devicons/devicon/blob/master/icons/typescript/typescript-original.svg" title="Typescript" **alt="Typescript" width="40" height="40"/>
</div>

---

### :fire: My Stats :

[![GitHub Streak](https://streak-stats.demolab.com/?user=luisherreralg&theme=default)](https://git.io/streak-stats)

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=luisherreralg)](https://github.com/anuraghazra/github-readme-stats)

---

### :writing_hand: Blog Posts :
This section will show the recent blog posts published by a GitHub user at different blogging platforms. To achieve this, we’ll create a GitHub workflow, which is an automated process to execute jobs. Each job in a workflow will have one or more actions. A GitHub action is a set of executable commands combined into steps. We can either create our own GitHub action or use an action created by some other user.

To fetch the blog posts, we’ll use two already existing actions:

Checkout: used to check out all the files in the current repository to a Git workspace where our workflow can access it.
Blog Post Workflow: used to fetch recent blog posts published by a user on various websites.
The workflow can be run on a specific schedule or an event trigger. For this tutorial, we’ll execute the workflow every one hour, to fetch the recent blog post. You can read more about GitHub actions from the official documentation.

To configure the GitHub workflow, follow these steps:

Add the following code to your README.md. The workflow will replace the comment below with the list of published blog posts:
<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->
Save the changes by clicking on the Commit changes button.
The configuration of GitHub workflow is defined in a .yml file, which follows a YAML syntax. In your repository, in the Add File dropdown, select Create New file.
Create new file in GitHub
In Name your file.. field, enter .github/workflows/blog-post-workflow.yml. All GitHub workflow’s .yml configuration files reside under the .github/workflows directory.
Create blog post yml file
Add the following code in the Edit new file tab:
name: Latest blog post workflow
on:
  schedule:
    # Runs every hour
    - cron: '0 * * * *'
  workflow_dispatch:

jobs:
  update-readme-with-blog:
    name: Update this repos README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gautamkrishnar/blog-post-workflow@master
        with:
          max_post_count: "4"
          feed_list: "https://dev.to/feed/itszed0"
In the above code, we’ve defined a workflow with name as “Latest blog post workflow”, which runs on a schedule mentioned in the cron field. 0 * * * * is a POSIX cron syntax, meaning that the schedule is to run at the 0th minute every hour.

workflow_dispatch: allows the user to trigger the workflow manually. jobs let us define one or more jobs that will run when the workflow is executed. In our case, we have one job — that is, update-readme-with-blog — which runs-on an Ubuntu environment machine hosted by GitHub.

steps define a set of actions or commands to be executed. We’ve defined two actions under steps: actions/checkout@v2 and gautamkrishnar/blog-post-workflow@master. The latter takes two input parameters defined under the with field. max_post_count defines the maximum number of posts to show in the README, feed_list is a comma-separated RSS feed of URLs for different blogging platforms.

In this tutorial, we’ve fetched blogs from the dev.to platform. For the list of all supported platforms, check this documentation.

To learn more about GitHub workflow syntax, check out this Workflow Syntax documentation.

Replace the feed_list with your RSS feed URLs and click on the Commit new file button. This will successfully create the workflow. It will fetch new blog posts from dev.to and add them to your README.md file every hour.

To trigger the workflow manually, follow these steps:

In your repository, go to the Actions tab.
Under All workflows, click on Latest blog post workflow.
In the Run workflow dropdown, click on the Run workflow button. The workflow will start executing.
Run Blog post workflow
Go to your GitHub profile page, and under the “Blog Posts” section you’ll see a list of all the blog posts from the blogging platforms defined in the blog-post-workflow.yml file. Below is the output for "https://dev.to/feed/itszed0" in the feed_list.
Blog posts
Note that the user itsZed0 has one article titled “Test Post” at dev.to, which can be found here. Hence, the workflow fetches that one article and displays it in the GitHub profile README.

The final GitHub profile is pictured below.

GitHub profile readme GIF
Conclusion
In this tutorial, we’ve learned what a GitHub profile README is and how to:

create a GitHub profile README
add GIFs, descriptions, skills
add GitHub Streak Stats and GitHub Readme Stats
create a GitHub workflow to fetch the latest published blog posts
I hope this tutorial inspires you to create an amazing GitHub profile README. Also, you can go through these open-source projects that’ll let you add some more cool features to your GitHub profile README:

Display weekly Dev metrics
Display Spotify recently played song card
Show a new programming joke every day
Share This Article





Nida Khan
Nida Khan
I am a full stack developer from India. I am a hands-on learner, hence prefer learning new technologies through development. In my free time, I explore new technologies, read tech blogs and solve problems on Data Structures and Algorithms.

career
career-advancement
git tutorial
github

The Unix Bible
