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

|
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
**Challenge**: SSH runs the internet. Connect to utkwrgubhj.qualifier.hackabit.com on port 22 with user hackerman and the provided private key.

**Key**: <a href="https://github.com/CodeAPretzel/Hack-A-Bit-2023/blob/main/Assets/id_rsa">Go to File</a>

|
<br>

**Solution**: The point of this challenge is for the challenger to learn about connections with private and public keys and how to gain access into a session using one of the keys. To begin with, after downloading the key, we are told in the challenge that we will have to use SSH (secure socket shell) on port 22, which SSH runs on default. In order to use a key with SSH for a session we use the -i parameter for the following command:

<br>

```
  ssh -i id_rsa hackerman@utkwrgubhj.qualifier.hackabit.com  #make sure you go to the directory where you saved your file
```

<br>

However you'll notice that when running this, the session doesn't accept this because the key has too many accessible permissions. To reduce the permissions needed for the session to just read the key, we will use the command bellow:

<br>

```
  chmod 400 id_rsa
```

<br>

After this we will just run the first command and get the output: **flag{shesellsseashellsbytheseaaaaaaashore}**

<br>

*Side Note: I tried running these commands on the actual session but it appeared to be down.*

<br>
<br>

## - Loading 🌀 -
**Challenge**: What's in this ISO thing?

|
<br>

**Solution**: With this challenge we are given the same Docker container from the Captain challenge. With no clue on what the challenge has in store, let's see what information we can get from extracting the image from the container and saving it to our system using the command below.

<br>

```
  docker save nathanielsinger/hackabit0x01-infrastructure-container1 > image.tar
```

<br>

Finally, like a .zip file but without compression, we have to unpack the .tar file using the following command:

<br>

```
  tar -xvf image.tar
```

<br>

After that the file will go into the directory you're in. Find the folder 89552...ea423 and the file layer.tar. Unpack the tar `tar -xvf layer.tar`
<br>
With that you go to from `root > flag_image.iso` then `cat FLAG.TXT`
<br>
Getting the output: flag{consider_it_loaded_hackerman}

<br>
<br>

## - Location 🌎 -
**Challenge**: Now with the same image, dive on in and find the iso image. What is the absolute path to the iso image stored within the container? Include the filename in the path for your submission.

<br>
<br>

## - Connector 🔌 -
**Challenge**: Connect to the mysql server at dyxvqmjwaj.qualifier.hackabit.com and read out the flag. Here are some user accounts:

<ul>
  <li>user1:uyqhxgxcxd</li>
  <li>user2:ehaigdexhh</li>
  <li>user3:xfgyuvtapt</li>
  <li>user4:tnvgijqxei</li>
  <li>user5:hybplwmndy</li>
</ul>

<br>
<br>

## - Boat ⛵ -
**Challenge**: Sometimes we need to run a machine on a specific address or virtualize a network, get this running on: 172.22.1.11.

**Container**: https://hub.docker.com/r/nathanielsinger/hackabit0x01-infrastructure-container2

<br>
<br>

## - Inspector 🔍 -
**Challenge**: Oh look its Bits, something changed though... see if you can track it down.

**File**: <a href="https://github.com/CodeAPretzel/Hack-A-Bit-2023/blob/main/Assets/bits.zip">Go to File</a>

"You will find in the files that there are logs"

<br>
<br>

## - Hammer 🔨 -
**Challenge**: Check out oslyxpzcgs.qualifier.hackabit.com and see if you can find the vuln. No help on this one, nothing crazy though... enumerate harder :)

The flag is stored in an environment variable.

<br>
<br>
