# DeepBrain Chain AI User

[README.md](https://raw.githubusercontent.com/DeepInThought/ai-user-linux/master/README.md)

The purpose of this repository is to spin up a Docker image with the AI User application.

We utilize docker-app for simplicity.  See [docker-app](https://github.com/docker/app) for more details.

1. [DeepBrain Chain AI User](#deepbrain-chain-ai-user)
	1. [Source Code](#source-code)
	2. [Docker Hub](#docker-hub)
	3. [Installation](#installation)
	4. [About Us](#about-us)
	5. [Code of conduct](#code-of-conduct)
		1. [Licensing Information](#licensing-information)

## Source Code

Repository Home: [https://github.com/DeepInThought/ai-user-linux.git](https://github.com/DeepInThought/ai-user-linux.git)

## Docker Hub

The Docker Hub is located at [https://hub.docker.com/r/deepinthought/ai-user-linux/](https://hub.docker.com/r/deepinthought/ai-user-linux/)

## Installation

[![asciicast](https://asciinema.org/a/KLDeG0OAGSg6Y0cdzfD7Ko6hn.svg)](https://asciinema.org/a/KLDeG0OAGSg6Y0cdzfD7Ko6hn/?speed=2)

`Run the following docker command in shell.`

```bash
docker pull deepinthought/ai-user-linux
```

`If using docker for run you will need to pass a volume mountpoint to use to maintain persistence with the node id.`

```bash
docker run --rm -it --volume "dbc-ai-user-volume:/dbc-ai-user"  --name dbc-ai-user --hostname dbc-ai-user deepinthought/ai-user-linux:latest
```

>**[Important]** **GENERATE A NEW NODE ID!** the image contains a unique one at build time.

```bash
dbc>>> system echo yes | /dbc-ai-user/0.3.4.1/dbc_repo/dbc --init
```

*****TODO:***** implement a unique node id after container launches.

`If using docker-compose:`

```bash
docker-compose -f docker-compose.yml up
```

`If using docker-app:`

```bash
docker-app render | docker-compose -f - up
```

>**[Important]** Make sure you backup the node.dat contents!

```bash
dbc>>> system cat /dbc-ai-user/0.3.4.1/dbc_repo/dat/node.dat
```

```bash
node_id=4cxpBfFM8u5fp8FpAFFgA5gWFMfcMH4ux55WbcB48CH5
node_private_key=88NJ3m458HAbgx81kgC41g4JFAAfrxgWNck5MpgMmF1P4M45328mWcgA1MMPcbgABBfCFx1F8X2A8FGFHg8MfB8cbHC5Ca4GN8bWBM8BWsMrp8p85pWpaf834W1apg4aPPW84HCHGM88fk8Mk8HPFWgfpJmb4XNuPPFJ4uBHFsNN8HfFCmuR3MBuMfaFPM5gWfxcCJ8XP5fHBbWR4WBBHp183ap5CfcMC3BCWffPua4W3W853bkXgCAMHBaMR83838PFAfxPGBs5gkF3WmpCN3fksH5C5xJHC5M88CppC4Hgxq
```

## About Us

Visit [README.deepIT.md](README.deepIT.md) for more information on [@DeepInThought](https://github.com/DeepInThought).

## Code of conduct

Checkout our [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for contributors.

### Licensing Information

Please visit: [LICENSE.md](LICENSE.md).