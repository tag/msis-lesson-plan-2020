# HTMl & CSS (with some Docker)

*[ ] Quiz #1
*[ ] Quiz #2 TODAY
*[ ] Quiz #3 MONDAY

*[ ] Show "D&S Tutorials" Canvas page

## Last time (Review!):

* Server architecture
* Virtual machines

* Review GitHub group assignment

## Version Control Systems

* Key phrases to know re git
  - clone / checkout
  - "two-phase commit"
  - push
  - pull, pull request
  - branch


* Show Git controls in Atom
  - Git repositories can be created in two ways:
    - local-to-remote
    - remote-to-local

* Show `.git` hidden folder
* `.gitignore` config

### Local to remote
  * Create the local repo
  * Two phase commit (commit & push)
  * Use Github desktop to create the remote repo

### Clone from remote server
  * (If you don't have commit permissions, ) Fork
  * Checkout/clone via GitHub Desktop
  * This is what you (probably) did for the first group project


How does it work if someone else pushes to master (if you're in a different branch)?

# Docker

## Terminology

  * **Image** : a static "picture" of a container
  * **Container** : a running image

```bash
> docker run [image name]
> docker run hello-world

# Shows available images
> docker images

# Shows running containers
> docker ps
# Shows all (including stopped) containers; see also Desktop
> docker ps -a
```

I _greatly_ prefer using `docker-compose`:
```bash
> docker-compose up --build
# Or, if you want to run it in the background
> docker-compose up -d --build
# Now list all the containers running
> docker-compose ps

```

Getting inside the running container:
```bash
docker-compose up -d

docker exec -it [container ID] bash

```

# Representing data: XML, JSON, CSV
What we need is a way to **serialize** data. In other words to be able to write it to a bit stream, and read it back in again. If we can serialize data, we can write it to a file or send it over the network.

```javascript
[
  {
    id: 123456789
    name: "Tom"
    classes: [
      {
        id: "BUS-X501"
        name: "MSIS Core"
      },
      {
        id: "PHL-A 890",
        name: "Intro to Being Awesome"

      }
    ]
  }
]
```


# Course project (in-class)
  * Remember: where we're going in the course (long version)
    - Full-stack application
      . Mobile ready (responsive)
      . Cloud
      . n-tier
      . Web services, API

## Let's begin to design an application

### Data model first!
* This creates design decisions.


  * Ask groups to make preview sketches

  * Show my preview sketches (5/25)

    - Build HTML?

## Open Atom
  * Create new folder!
    - Describe folder structure

  * Build an HTML file
      - Describe Document Object Model
      - doctype
      - head, title (required!), body

  * Add Bootstrap
      - Show [Bootstrap's grid layout](https://getbootstrap.com/docs/4.1/layout/grid/)

  * Block elements vs inline elements
      - Include style for divs (border, bg-color), and add placeholders
      - Show style by tag, class, id
      - Show Atom's HTML preview!

  * CSS selectors
    - element (tag) name
    - id
    - class
    - combination selectors
      - descendant
      - immediate descendant
      - ::hover, ::link
