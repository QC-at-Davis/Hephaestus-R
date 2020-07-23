# Hephaestus-R

A variant of [Hephaestus](https://github.com/Quantum-Computing-at-Davis/Hephaestus) targeted towards protein mapping research.

__NOTE__: Hephaestus-R was originally EQEnv, developed independently by [johnzl_777](https://github.com/johnzl-777/EQEnv) before being archived and properly transferred under Quantum Computing at Davis (QCaD) control.

## Difference from Hephaestus

The original Hephaestus environment was designed to be as small and fast as possible, with an emphasis on running workshop content.

Hephaestus-R has opted to remove some of the educational packages as well as consideration on space in favor of having as many possible tools available for users.

## Usage

Ensure that Docker is installed on your machine and running in the background.

git clone and navigate to the directory where you cloned the repo.

Run the following:

```
docker-compose up
```

By default, port 8888 on your local machine is directly mapped to port 8888 in the container, which is the port Jupyter Lab uses. If this proves problematic (you have another Notebook or Lab instance running), you can create a variable in your shell environment called `JPORT` and set it to a port of your choice. The container and host will both automatically map to that new port. The new port will be properly displayed when you need to copy-paste the auto-generated Jupyter Lab URL.

## Development

If the underlying `Dockerfile` has been edited and new packages have been added (or removed), Docker will *not* rebuild the image. Instead it will run the last build.

To force a new build just run the following:

```
docker-compose up --build
```

If there is a lot of package "shuffling" (testing the addition/removal of packages in the Dockerfile) you may want to use 
```
docker-compose down
```
instead of the standard `Ctrl+C` exit procedure denoted by Jupyter. This deletes the container as well as the image created by up. It will keep anything defined in the shared folder.