<div align="center">
  <h1>
    💥 Hack-A-Bit-2023 💥
  </h1>
</div>

<br>

In the Hack-a-Bit (HaB) category infastructure, you will find the following challenges with their designated points:

<ol>
  <li>Captain (75 points)</li>
  <li>Seashell (75 points)</li>
  <li>Loading (100 points)</li>
  <li>Location (100 points)</li>
  <li>Connector (125 points)</li>
  <li>Boat (125 points)</li>
  <li>Inspector (150 points)</li>
  <li>Hammer (150 points)</li>
</ol>

With each challenge we will figure out the problems and how to solve each one:

<hr>
<br>

## - Captain 🌊 -
**Challenge**: Cloud infrastructure is migrating to containerized technology in many places, lets get started with containers. Run this docker container with the environment variable FLAG_ENABLER set to give_me_the_flag.

**Container**: https://hub.docker.com/r/nathanielsinger/hackabit0x01-infrastructure-container1

<br>

**Solution**: The point of this challenge is for the challenger to find a way to run the container with defining the set variable in the container. For this challenge you can use any updated distro of Linux. Before we could use the pull request in URL given, we first need to install the Docker packages necessary using the command line below (if we haven't installed them to begin with):

<br>

```
  sudo apt-get update
  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

<br>

After that we pull the container from the URL:

<br>

```
  docker pull nathanielsinger/hackabit0x01-infrastructure-container1
```

<br>

Afterwards, all we need to do is set the ENV. variable for the container which, after a google search later, we get the following command:

<br>

```
  sudo docker run -e FLAG_ENABLER=give_me_the_flag nathanielsinger/hackabit0x01-infrastructure-container1 #
```

<br>

This brings the output: **flag{you_aren't_the_captain_just_yet}**

<br>
<br>

## - Seashell 🐚 -


<br>
<br>

## - Loading 🌀 -


<br>
<br>

## - Location 🌎 -


<br>
<br>

## - Connector 🔌 -


<br>
<br>

## - Boat ⛵ -


<br>
<br>

## - Inspector 🔍 -


<br>
<br>

## - Hammer 🔨 -


<br>
<br>
