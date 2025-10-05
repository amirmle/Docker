Build image

    docker build -t myimage .
    
- myimage → tag assign to the image
  
- -t myimage → tag for the image
  
- . → build context (all files in current directory are available to COPY)


### defaul docker file name is Dockerfile

for diffrent names must use -f tag to decleare docker file 

    docker build -f Dockerfile.dev -t myapp-dev .

---


inside of docker file:

    FROM python:3.11-slim
      # choose a base docker image 
      # there can be only one base image (unless using multi-stage builds)
      # every base image is a lightweight and filesystem layer with its own minimal environment
    
      
    WORKDIR /app
      # sets the working directory inside the container's filesystem
      # if the directory exists, it will be used; if not, it will be created
      # example:
        /
        ├── bin
        ├── lib
        ├── tmp
        ├── usr
        ├── ...
        └── app  <-- created by WORKDIR
              ├── app.py  
              ├── requirements.txt
              └── ...
    
      # you can have multiple WORKDIR commands 
        WORKDIR /app
        WORKDIR src
          -> /app/src
    
      
    COPY . .
      # Syntax: COPY <src> <dest>
      # First . → all files and directories in the build context (the folder passed to docker build).
      # Second . → the destination path inside the container (here, the WORKDIR).
    
      
    RUN pip install -r requirements.txt
      # Runs a command during the image build.
      # Each RUN creates a new layer.
      # You can write several RUN instructions, but combining them with && is often better for optimization.
        
    CMD ["python", "app.py"]
      # Defines the default command that runs when the container starts.
      # Syntax options:
            CMD ["command", "param1", "param2"]   # exec form (recommended)
            CMD command param1 param2             # shell form
      # Only one CMD is allowed (the last one is effective).
      # To run multiple commands, create a bash script and call that script in CMD.
            COPY start.sh /app/start.sh
            RUN chmod +x /app/start.sh
            CMD ["/app/start.sh"]


# layers:

## why use layers?

- caching: if a command does not change, docker reuses that layer from cache onstead of rebuilding it → faster builds

- sharing: if multiple images use the same base image, docker download and store it only once 

- immutability : layers are read-only; only the top container layer is writable during runtime

- example:

  Layer 6: CMD instruction (metadata only)
  
  Layer 5: Project source code
  
  Layer 4: Installed Python packages
  
  Layer 3: requirements.txt
  
  Layer 2: /app working directory
  
  Layer 1: Python base image
  
  ─────────────
  
  Kernel: from host (shared, not inside image)
  



### RUN → executed at build time (to bake things into the image).

### CMD → executed at container runtime (to define the container’s default behavior).

### If you pass a command manually to docker run, it overrides CMD.

### Layers are cached: if nothing changes above a layer, Docker won’t rebuild it.
