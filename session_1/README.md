Create a VM in the cloud.

We have many different parameters to pick from:

a. pick a name (homl-vj)
b. pick a region (us-west1)
c. pick the cpu/memory profile 4-vCPUs, 15 GB RAM (n1-standard-4)
d. pick the OS (Ubuntu 18.04 LTS)
e. pick disk (50GB)

Create the VM.

Next, we will install Docker.

The instructions are at: https://docs.docker.com/install/linux/docker-ce/ubuntu/
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
This will install Docker. We can test if docker is installed correctly by doing:
```
sudo docker run hello-world
```
This will run the hello-world container, and since it doesn't exist yet, it will be downloaded.

You should see an output like this:

Hello from Docker!

Run "docker images" to see the newly downloaded image. If you run it again, it should now run locally.

Do we have python installed in our VM?
Which version?

Next, let's build a Docker container where we can specify the exact environment we need for our DS/ML work.

The git repo has a Dockerfile. Build the docker image:
```
docker build -t pycontainer .
```
This downloads a lot of stuff. 
Why?
How can we reduce the amount of stuff it downloads?

Next, run the container:
```
docker run --rm -it pycontainer bash
```
What is this command doing?

Once inside the container, try running python.
Can you import numpy?
How can we get numy in our container?

Next week we get Jupyter running in our container.
Commit all changes to git.
Remember to power down your VM.
