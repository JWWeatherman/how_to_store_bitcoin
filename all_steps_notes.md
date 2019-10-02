


- Go to our website on any laptop.
- Follow the get started instructions wizard and install Ubuntu.



- On the online laptop go to our website and download and run yeti.sh
- yeti.sh will install flask.
- yeti.sh will install our flask app.
- yeti.sh will open the flask app in firefox.
- ask the user if we can install
    - qrtools
    - bitcoind
- give status on bitcoind installation.

- execute bitcoind, and wait for it to sync the blockchan. It will regularly check to see if the blockchan is up to date.
    - ./bitcoin-cli getblockchaininfo and look at "verification progress"
    - using bitcoinsetup.sh
- one completed it will move to the next screen.
- generate a random number for the rpc password and update bitcoin.conf
- restart bitcoind

- repack all of the installed items.
- tell the user to copy the repack folder to their external drive and copy to the disconnect laptop.
- using these exact steps package up everything:
    $ sudo apt-get install dpkg-repack fakeroot
    $ mkdir ~/dpkg-repack; cd ~/dpkg-repack
    $ fakeroot -u dpkg-repack `dpkg --get-selections | grep install | cut -f1`
- move the package and the bitcoin installer and the .bitcoin directory into a folder on the desktop named "toDisconnected"
- instruct user to copy toDisconnected to the LARGE external hard drive and then to the desktop of "disconnected"

from online latop to toDisconnected folder
1. FlaskApp directory (includes bitcoin core installation)
2. .bitcoin directory
3. dpkg-repack directory

- on disconnected laptop, after the user has copied the folder from the LARGE drive to the desktop, open a terminal and type
cd ~/Desktop/toDisconnected/dpkg-repack/
sudo dpkg -i *.deb

cp -a ~/Desktop/toDisconnected/.bitcoin/. /~
cp -a ~/Desktop/toDisconnected/flaskapp/. /~



- now copy over bitcoin core application to home.
- copy the .bitcoin directory. This will take some significant time so let's see if we can show a status.
    and then start bitcoind (might need to start/stop bitcoind before copying over the directory if this causes errors).
- Generate and store the private keys.
- import each key using "importprivkey <your_wif_private_key> 1_key"
- Grab the public keys by using get getaddressbylabel 1_key (replace 1 with the key number).
- Run the command addmultisigaddress 3
  "[\"first_public_key_here\",\"second_public_key_here\",\"third_public_key_here\",\"fourth_public_key_here\",       \"fifth_public_key_here\",\"sixth_public_key_here\",\"seventh_public_key_here\"]"
- Display the command in a QR code and instruct the user to scan it using the online laptop.

- On the online laptop instruct the user to scan the qr code to capture the command to create the multisig address. Check to make sure the resulting data starts with "addmultisigaddress" and if it does store it in the "to_print_file.txt"

- On the diconnected laptop the user clicks next and we display the redeem script qr code and insruct them to scan with the online laptop.

- On the online laptop scan and make sure it looks like a redeem script. 

- One the diconnected laptop the user clicks next and we display the multisig address.

- On the online laptop scan the qr code displayed on the disconnected laptop. 

