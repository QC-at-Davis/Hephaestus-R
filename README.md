# Hephaestus-G

A variant of [Hephaestus](https://github.com/Quantum-Computing-at-Davis/Hephaestus) targeted towards protein mapping research.

## Difference from Hephaestus

The original Hephaestus environment was designed to be as small and fast as possible, with an emphasis on running workshop content.

Hephaestus-G has opted to remove some of the educational packages as well as consideration on space in favor of having as many possible tools available for users.

## Usage

Ensure that Docker is installed on your machine and running in the background.

git clone and navigate to the directory where you cloned the repo.

Run the following:

```
docker-compose up
```

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