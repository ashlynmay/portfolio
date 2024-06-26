<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

<!-- PROJECT LOGO -->
<br />
<div align="center">
<h3 align="center">Portfolio Web App</h3>

  <p align="center">
    A portfolio web app built in Flask utilizing tailwindcss and daisyUI.
    <br />
    <a href="https://ashlynmay-github-io.onrender.com/">View Demo</a>
    ·
    <a href="https://github.com/ashlynmay/portfolio/issues/new?labels=bug&template=bug-report---.md">Report Bug</a>
    ·
    <a href="https://www.youtube.com/watch?v=fr1VH-YGzcw">Video Demo</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li>
    <a href="#explanation">Explanation</a>
    </li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Portfolio Screen Shot][product-screenshot]](https://ashlynmay-github-io.onrender.com/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

* [HTML5]
* [JS]
* <a href="https://tailwindcss.com">[tailwind CSS]
* <a href="https://daisyui.com">[daisyUI]
* <a href="https://flowbite.com/">[Flowbite]

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

The project is pretty simple to set up.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* python (ubuntu)
  ```sh
  sudo apt update
  sudo apt install python3
  python3 --version
  ```
* pip (ubuntu)
  ```sh
  sudo apt install python3-pip -y
  pip3 -V
  ```
* node.js (ubuntu)
  ```sh
  cd ~
  curl -sL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource_setup.sh
  sudo bash /tmp/nodesource_setup.sh
  sudo apt install nodejs
  node -v
  ```
* flask
  ```sh
  pip install flask
  ```
* cs50 python library
  ```sh
  pip install cs50
  ```

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/ashlynmay/portfolio.git
   ```
3. Enter porfolio directory
   ```sh
   cd portfolio
   ```
<a href="https://tailwindcss.com/docs/installation">4. Install Tailwind CSS<a/>
<br>
<a href="https://daisyui.com/docs/install/">5. Install daisyUI<a/>


<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Explanation

### Layout
Responsive layout depending on screen size.
  Mobile devices will have a bottom navigation bar, whilst desktop devices have a topbar. (both from daisyUI)
    The different states of the navigation bar, depending on what page they are on are stored as btm-nav(none), nav-contact(contact me), nav-home(homepage), and nav-projects(projects pages).
  A footer is included in footer.html and is passed through into layout.html to ensure it is in each page. (footer from Flowbite)

### Homepage
Homepage features a hero component from daisyUI.
  The hero include a photo of me, two sentences about myself inside of a code mockup component from daisyUI, and a button to go to the projects page.
It also features a timeline component from daisyUI.

### Projects
The main projects page will show featured projects.
  These projects data are stored in `projects/project_name.md` and are formatted as so:
  ```sh
   title of project
   link to preview image
   brief description
   project repo link
   type of project (c, python, web, or other)
   whether or not the project is featured or not (0 or 1 for false and true respectively)
   alt text
   ```
Upon loading the main projects page, it will *always* drop the `projects` table to ensure it is up to date, and then will call the function `project_check()` which will check if there is an existing table named `projects`, and if not create one, and then append the data inside the `project_name.md` file to a SQL table named `projects`, located in `portfolio.db`.

After `project_check()` has completed, the categories of *featured* projects (c, python, web, or other) will be split into their own python dictionaries which will be included when finally `render_template("projects.html" c_projects=c_projects ...)` is returned.
When clicking on "View More Projects in ______", it will send the user to a very similar page but containing all projects of the said type of project. 

### My Cat
A simple page utilizing the masonry image grid component from Flowbite to show off pictures of my cat.

### Resume
A button that redirects the user to my indeed resume.

### Contact Me
A simple page with a photo of me, my name, a button to email me, and my various socials.

### 404
A page that will show up whenever the error handler returns error 404. It is from Flowbite, but restyled for the theme.


<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[product-screenshot]: https://res.cloudinary.com/dpm4kmh00/image/upload/v1714263510/portfolio%20assets/portfolio_hrxkzn.png

