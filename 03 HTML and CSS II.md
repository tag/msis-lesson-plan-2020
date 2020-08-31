# Case competition review

* We love you, even if it comes across as harsh
    - This is a safe place
* Answer the right question
    - This was about how to *manage* the project, not how to *do* the project
* Appendices. Always
* Accepting feedback

# Common HW issues

### File paths
Relative file paths as used in `<link>`, `<img>`, `<a>`, and scripts.
    * Absolute, from root
        - Leading `/`
    * Relative
        - `../` back up a level
    * Common protocol
        - `://`
    * Fully qualified
        -`[protocol]://[domain]/[path]/[file]`
    * Do NOT use paths specific to your drive

# Three parts to design an application:
[Draw this on the board]

  1. UI (Presentation Layer)
  2. Application logic
  3. Data store

## The architecture of our system

* Separation of Concerns: What is the role of HTML, CSS, Javascript
    - [CSS Zen Garden](http://www.csszengarden.com)
      . 

* MVC, and which parts are represented where in our architecture.


## DOM: What is it?

* div, rows and columns
* Use `<section>`?


# Docker

https://docs.docker.com/get-started/

image == class
container == instance

    > When you run docker run `hello-world`, Docker looks for the image locally. 
    > If the Docker image doesn’t exist, Docker “pulls” the image and then runs 
    > it. After the image is downloaded, run docker images to see the 
    > `hello-world` image locally

```bash
$ docker run hello-world

\# Read the output!

\# List the loaded images
$ docker images
```

Use `docker-compose build app` to build this docker image, when in this project
directory.

Use `docker-compose up` from the project directory to run the container.

After running this image, the web page should be visible at http://localhost:8080/

The file `docker-compose.yml` maps the container's port 80 (default web port) to
the host's (that's your machine's) port 8080 with the `ports` command.

The `volumes` command in `docker-compose.yml` maps the your folder `app` to the
container's `\srv\app\` folder. Changes made in one place will be made in the
 other.

 The key combo `ctrl-C` will kill the container.

### File paths
Application code will go in `app`.

Publicly viewable pages will go in `app/public`

### More Docker commands

```bash
\# Won't work, as the image is running
$ docker rmi <image number>
  
$ docker ps     # Lists _containers_
$ docker ps -a  # Even shows the stopped ones

\# removes the container
$ docker rm <container number>
  
\# Enters the container
$ docker exec -it 8a34fd460cec bash
```
