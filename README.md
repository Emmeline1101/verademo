# VeraDemo - Blab-a-Gag

## About

Blab-a-Gag is a fairly simple forum type application which allows:

- Users can post a one-liner joke.
- Users can follow the jokes of other users or not (listen or ignore).
- Users can comment on other users messages (heckle).

### URLs

- `/feed` shows the jokes/heckles that are relevant to the current user.
- `/blabbers` shows a list of all other users and allows the current user to listen or ignore.
- `/profile` allows the current user to modify their profile.
- `/login` allows you to log in to your account
- `/register` allows you to create a new user account
- `/tools` shows a tools page that shows a fortune or lets you ping a host.

## Running the Project

1. Verify you have docker installed via `docker ps`

2. Download the project via

   ```
   git clone https://github.com/YuqiHuai/verademo
   ```

3. Navigate to the root directory of the project via

   ```
   cd verademo
   ```

4. Build the project via

   ```
   docker build -t verademo .
   ```

   > This command looks at the Dockerfile in your current working directory
   > (i.e., after you run cd verademo, your current working directory is verademo)
   > and builds a docker image based on that Dockerfile. Docker image allows docker
   > to create a container, a container is a lightweight virtual machine.

5. Run the project via

   ```
   docker run -p 8080:8080 -it verademo
   ```

   > This command creates a container based on the image named verademo
   > (i.e., the one you built in the previous step), and binds port 8080
   > of your local machine to port 8080 of the container, so if you open
   > a browser and go to http://127.0.0.1:8080, you are viewing the content
   > from port 8080 of the container.

6. Navigate to: http://127.0.0.1:8080

## Exploitation Demos

See the `docs` folder.

## Technologies Used

- Spring boot
- MariaDB

## Workflow when doing the assignment

The assignment asks you to run the project, understand some of the exploits,
and try to fix them. Therefore you are expected to read the source code of the
project, and make some modifications to mitigate the threat.

So the first thing you do is to run `git clone ...` to download the project.
After doing so, you can find the source code of the project under `verademo/app`.

You build the project by running `docker build ...` , run the project by running
`docker run ...`, and go to http://127.0.0.1:8080 to explore the web app.

After you have explored enough and understood the exploits, you modify the source
code in `verademo/app` to mitigate some of the threats. Each time you modify the
source code you need to rebuild the project by running `docker build ...` and rerun
the project by running `docker run ...` to see the effect of your changes.

You must rebuild and rerun the project to see your changes.

## Quick Commands using Makefile

To simplify commands for using Docker, a Makefile is provided with the following commands:

- `make clean` will stop and remove all docker containers
- `make build` will build the docker image
- `make run` will run the built docker image
- `make restart` will rebuild the image and restart the container
