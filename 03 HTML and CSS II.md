# Quiz #2; Review Quiz #1

# Common HW issues

### File paths
Relative file paths as used in `<link>`, `<img>`, `<a>`, and scripts.
    * Absolute, from root
        - Leading `/`
        - Leading with a drive letter `C:\`
    * Absolute, from user directory (Unix, Mac; not Windows)
      - Leading '~/'
    * Relative
      - No leading slash
      - `./` go from the current directory
      - `../` back up a level
    * Common protocol
        - `://`
          - e.g., `://css/styles.css`
    * Fully qualified
        -`[protocol]://[domain]/[path]/[file]`
          - e.g., http://localhost:8080/css/styles.css
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


## Internet stack (review)

5. Application Layer (HTTP)
4. Transport Layer (TCP -> Port 80/443)
3. Network Layer (IP)
2. Data Link Layer (wifi / Ethernet)
1. Physical Layer



## HTML Review

* div (block element), span (inline element)
* `<title>` element required!
* Use `<section>`?

### Tags you may not have learned about

* `<label>`
* `<cite>`
*

### Explain DOM tree, show a tree

* HTML validator: https://validator.w3.org/#validate_by_input


# Docker (Review from 02)

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
