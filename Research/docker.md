# What is Docker?

- Think of it like a package manager that works on any os
- Dockerfile is the recipe for the image creation
  - it starts with **FROM** that specifies from where
  - you create layers which get moved around
  - **Run:** Runs the command necessary to install
  - Each command spawns a mini layer to add back into the host linux image
  - docker build creates the image

## Docker Registry

- Universal app distrubition
- Standard for how containers are moved around
- Each image has a unique SHA Hash for the layers/metadata for that specific image
- **docker push** will push this image to the registry
- **docker pull** will pull the image to the host machine

## Docker Engine

- Runs in the background verifying image
- Image is run through **docker run**
- An app is ran in its own container
  - Built in a **namespace** which its ran in its own niche
  - Its cutoff from the rest of the is system
  - gets its own file system
- You can create two of the same containers but they won't be able to communicate
- Client communicates through various ways
  - Sockets
  - TCP/TLS
  - SSH Tunnel
- Separate containers need to run through a different host port when published
- **docker run -d -p 8800:80  public input port:  private listening
- docker run also pulls

## Why Docker

### The problem of Isolation

- Servers can waste a lot of resources if not fully utilized
- They can be hard to manage with so many different versions/apps on one app
- Hard to isolate these apps since they all share the same filesystem
- VM's allowed abstracion
- Containers allow Isolation similar to VM where they get their own IP, process space, and filesystem
  - but you don't need the full OS, MUCH simpler and safer  :()

### The Problem of Environments

- "it works on my machine"
- You may not have all the environments to test even though it works on yours
- For every part of an app and type of environemtn, there are different configurations
- consistent standard format now, OCI woot woot

### The Problem of Speed

- The speed of business is King
- The ability for business to execute their ideas
  - big part of the process lifecycle
- Distrubeted Architecture is King

