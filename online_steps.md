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

# Step X: Install Updates and Apps on ONLINE laptop

Install security updates.

Install qrtools.

Download and copy YETI to the LARGE external drive.

Download and copy Bitcoin Core to the LARGE external drive.

# Step X: Copy Installed Items from ONLINE to DISCONNECTED laptop 

We created a directory on your desktop named REPACK
that contains a copy of the installed items that 
need to be copied to your ONLINE computer.

Create a directory on your desktop named repack:
     mkdir repack.
Repackage all of your installed items using the command:
     fakeroot -u dpkg-repack 'dpkg --get-selections | grep install | cut -f1'
Copy the "repack" directory on your desktop.


# Copy the Multisig Address and Redeem Script to ONLINE laptop 
## disconnected and online

Use the addmultisigaddress command with the 7 public keys to generate a multisig.

Capture the address and the redeem script.

Display the multisig address on the disconnected laptop and copy it to the online laptop using a qr code.

Repeat for the redeem script.

# Print the guide
## online laptop
This will contain the instructions,
the redeem scirpt, 
the addmultisigaddress command used,
and space to include the private key.
