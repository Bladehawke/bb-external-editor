# Docker Setup

This guide assumes you are familiar with docker or at least have a basic understanding. The advantage of using Docker is simple: you don't have to have the dev tools (NodeJS and its dependencies) installed on your system. If you don't know what Docker is, please follow the instructions available in [README.md](./README.md).

## Basic intructions

1. Let's assume you have installed [Docker](https://www.docker.com/products/docker-desktop/).

2. Get a copy of this repository either via `git clone` or downloading a zip end extracting it somewhere.

3. Change into the working directory you created in the previous step.

4. I borrowed a trick from another project that allows us to get a new `NetscriptDefinitions.d.ts` for Intellisense autocompletion.  We're going to mount this file as volume and voila, it will get updated every time we launch the container and game.

   * For Linux/Mac users, type `touch NetscriptDefinitions.d.ts`

   * For the rest, type into Powershell `New-Item NetscriptDefinitions.d.ts`

   * For all, the filename is case sensitive, you might want to cut and paste it.

5. Build the container with: `docker build -t bb-external-editor .`

6. To run the container, just type `docker compose start bbee`

7. Bitburner > Options sidebar > Remote API > type in the port 12525 and click connect. The icon should turn green and say it's online.

8. To stop the container, type `docker compose stop bbee`

## Further thoughts

Please read the [Readme for the project](./README.md).

* By editing your files in an editor of your choice that supports Intellisense, you will get code completion suggestions as good as you get in the game, whether the container is running or not.

* You could leave the docker container running if you're not interested in starting it every time you play.

* Remember that your scripts "live" in the servers\hostname directory and back them up often.

* If/when bb-external-editor gets updated, you could refresh your directory, repeat steps 3-5 and be back in business.
