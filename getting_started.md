# Overview of Yeti Bitcoin Storage

Yeti Bitcoin Storage is designed
for long term bitcoin storage of significant amounts.

The process can be completed by non-technical users,
but will require several days of passive time 
(waiting for computers to work)
and about 4 hours of active time
(writing down words, installing software or flipping coins).

It uses generic hardware to avoid supply chain attacks
and bitcoin core to avoid software security flaws.

Private keys are never on an internet connected computer.

The 3 of 7 combination was selected
because we believe loss is more likely than theft.
By having a 3 of 7 setup four private keys
can be lost due to natural disaster or 
errors by custodians without losing your bitcoin.

Bitcoin private keys are stored on paper 
in multiple geographic locations
with professionals that do not know they are storing
bitcoin private keys.

Private keys are written down using the NATO phonetic
alphabet where every fifth word is a checksum
to reduce the possibility that a private key will
be unreadable when needed.

Bitcoin core does not support Bip39 due to security
and recovery concerns.

Instructions for recovering the bitcoin are included
with every copy of the private keys
to reduce the liklihood of loss. 

Private keys are generated with user provided entropy
and the small amount of code used to automate the process
is written in python to reduce the difficulty of 
security code reviews by trustworthy engineers. 

Hardware modifications to disable wifi cards
and microphones are not included,
but can be performed for additional protection.

# What step are you on?

This document will walk you through setting up
an DISCONNECTED laptop to generate and access your private keys
and ONLINE laptop for getting updated transaction data
from the bitcoin network.

What device are you using to read this?

I'm just getting started

I am reading this on my OFFLINE laptop

I am reading this on my ONLINE - DANGER laptop

# Step X: Gather Required Equipment
You will need the following:

1. Two laptops that can run Ubuntu and Bitcoin Core. 
At the time of this writing almost any laptop with at least
500 GB of disk storage will work well
and can be purchased for less than $200. 
At the end of this process one of the laptops will be destroyed
so keep this in mind when purchasing.

2. An external hard drive with at least 
500 GB
of disk storage that can connect to both laptops.

3. A second external hard drive with at least
10 GB
of disk storage than can connect to both laptops.

3. A printer and printer paper.

4. A box with at least 50 coins of the same type.

Once you have these items available click Next to continue.

# Step X: Label and Tape Your Laptops and Drives

Using a permanent marker write the word "OFFLINE" 
on both the outside and the inside of one laptop
and the words "DANGER - ONLINE" on the outside
and inside of the other laptop.

Use a piece of tape to cover the camera
and microphone of both laptops. 

Using a permanent market write the word "LARGE"
on your large external hard drive and "SMALL"
on your smaller external hard drive.

Once this is completed click Next to continue.

# Step X: Install Ubuntu

There are several guides online for installing Ubuntu
including this one:

https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#0

You will want to install Ubuntu by making your SMALL external drive 
bootable.

Never connect the DISCONNECTED laptop to any wifi network and disable the wifi
card in Ubuntu as soon as possible.

Be sure that you first delete and reformat all existing partitions
using the Disk utility that you can access by selecting
"Try Ubuntu" before installing Ubuntu.

Also do a "basic install" so that only the minimum required componensts are installed.

Once both laptops have Ubuntu installed click Next to continue.
