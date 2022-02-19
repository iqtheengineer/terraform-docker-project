<div id="top"></div>
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
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
 


<h3 align="center">Terraform Deployment - Docker Container with Nginx Web Server</h3>
  <p align="center">
    Automating With Terraform
    <br />
    <a href="https://github.com/iqtheengineer/gcp-terraform-project"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/iqtheengineer/gcp-terraform-project">View Demo</a>
    ·
    <a href="https://github.com/iqtheengineer/gcp-terraform-project/issues">Report Bug</a>
    ·
    <a href="https://github.com/iqtheengineer/gcp-terraform-project/issues">Request Feature</a>
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
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project


Terraform is an open-source infrastructure as code software tool that enables you to safely and predictably create, change, and improve infrastructure. The cloud computing tool assists in building, modifying, and versioning infrastructure in a secure and efficient manner.

In this project I crafted a Terraform file to automate the process of creating a Docker container that runs a Nginx web server image.


<p align="right">(<a href="#top">back to top</a>)</p>



### Built With

* [Terraform](https://www.terraform.io/)
* [Docker](https://www.docker.com/)
* [Nginx](https://www.nginx.com/)


<p align="right">(<a href="#top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started
These are instructions for Windows Users. To gather instruction for other OS please visit https://learn.hashicorp.com/tutorials/terraform/install-cli?in=terraform/gcp-get-started

WINDOWS - To get started you would want to make sure you have the following utlities installed: <br><br>

- Terraform
- Docker
- WSL2



### Steps

Create a directory named learn-terraform-docker-container.
* 
  ```
  mkdir learn-terraform-docker-container
  ```
Then navigate into it.
  ```
  cd learn-terraform-docker-container
  ```
Paste the following Terraform configuration into a file and name it main.tf

  ```
  terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = ">= 2.16.0"
    }
  }
}

provider "docker" {
}

resource "docker_image" "nginx" {
  name         = "nginx:latest"
  keep_locally = false
}

resource "docker_container" "nginx" {
  image = docker_image.nginx.latest
  name  = "tutorial"
  ports {
    internal = 80
    external = 8000
  }
}

  ```

Then initialize the project.
  ```
  terraform init
  ```
And finally provision and push the configuration.
  ```
  terraform apply
  ```

If all goes well you should see the Nginx container running of localhost:800 or by running docker ps.

After that is done, be sure to stop the container and destroy the Nginx webserver.
   ```
  terraform destroy
  ```





<!-- USAGE EXAMPLES -->
## Usage


_For examples, please refer to the [Documentation](https://learn.hashicorp.com/tutorials/terraform/install-cli?in=terraform/gcp-get-started)_

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap


See the [open issues](https://github.com/iqtheengineer/gcp-terraform-project/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTACT -->
## Contact


Project Link: [https://github.com/iqtheengineer/gcp-terraform-project](https://github.com/iqtheengineer/gcp-terraform-project)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->


<p align="right">(<a href="#top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/iqtheengineer/gcp-terraform-project.svg?style=for-the-badge
[contributors-url]: https://github.com/iqtheengineer/gcp-terraform-project/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/iqtheengineer/gcp-terraform-project.svg?style=for-the-badge
[forks-url]: https://github.com/iqtheengineer/gcp-terraform-project/network/members
[stars-shield]: https://img.shields.io/github/stars/iqtheengineer/gcp-terraform-project.svg?style=for-the-badge
[stars-url]: https://github.com/iqtheengineer/gcp-terraform-project/stargazers
[issues-shield]: https://img.shields.io/github/issues/iqtheengineer/gcp-terraform-project.svg?style=for-the-badge
[issues-url]: https://github.com/iqtheengineer/gcp-terraform-project/issues
[license-shield]: https://img.shields.io/github/license/github_username/repo_name.svg?style=for-the-badge
[license-url]: https://github.com/github_username/repo_name/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/iman-crooks
[product-screenshot]: downloads/ImanCrooks1_whiteBG.gif
