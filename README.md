# Procedure
This document provides instructions
for creating and recovering a mulitsignature
address.

## What you need:
1. ONLINE laptop with Ubuntu, bitcoin core, this text file, and a printer.
2. Offline laptop with Ubuntu and bitcoin core.
3. External usb hard drive.

## Prepare Laptops 

###Install Ubuntu
1. On both laptops using the usb drive.
2. Turn off wifi and bluetooth on the "Offline" computer.

### Install QtQR and Bitcoin Core 
QtQR is an application to create and read QR codes.
It will be used to transfer data to and from 
the Offline Computer.

1. On the ONLINE Computer in the terminal window type:
    sudo apt install qtqr

TODO: -- Need to add the step to patch qtqr for saving images --

2. Navigate to your desktop using a command like:
    cd /home/bob/Desktop (this assumes your username is bob).
3. Create a directory on your desktop named repack:
    mkdir repack.
4. Repackage all of your installed items using the command:
    fakeroot -u dpkg-repack 'dpkg --get-selections | grep install | cut -f1'
5. Copy the "repack" directory on your desktop.
6. Download and install bitcoin core from:
    https://bitcoincore.org/en/download/
7. Be sure to turn off 
6. On the ONLINE Computer open a terminal window and navigate to the "repack" directory using:
    cd /home/bob/Desktop (this assumes "bob" is your username).
7. Install all packages in the directory using the command:
    sudo dpkg -i *.deb

### Generate 7 private keys and prepare paper backups
1. Print out the sheet locted at --TODO URL to the doc--
2. Flip a coin. The side displayed will be used for the number 1.
3. Place at least 50 pennies in a box and shake vigerously.
4. Grab a handful of coins and Using the printed sheet write down a 1 or a 0 for each coin result.  For each underlined section write down 5 numbers. This will give you a total of 256 "bits" ink your private key.
5. Using the python script on the OFFLINE machine convert the first binary number into a bitcoin WIF formatted private key.
6. Paste each of the WIF formatted private keys into the OFFLINE.txt document into the section titled "Private Keys."
6. Using the bitcoin console on the OFFLINE machine type "importprivkey <your_wif_private_key> firstkey" and hit Enter.
7. Now type "getaddressbylabel firstkey" and hit Enter.
8. To get your public double click the first address displayed, copy the address by double clicking it and typing ctrl-c. At the prompt type "getaddressinfo " and then right click and select Paste and then press Enter.
9. In the information displayed under "pubkey" you will see your public key for your first private key. Double click the public key and use ctrl-c and ctrl-v to copy the public key into the "OFFLINE.txt"" document under section titled "Add Multisignature Address with Public Keys."
10. Repeat steps 7 through 9 and use "secondkey" "thirdkey" and so forth. 
11. Paste the command in the "Add Multisignature Address with Public Keys" into the bitcoin-qt console and click Enter.
12. The console will return the multisignature address. Copy and paste it into the section titled "Returned Multisignature Address" into the "OFFLINE.txt" file.
13. Open QTQR and paste in the command under the "OFFLINE Add Multisignature Address with Public Keys" section.
14. On the ONLINE machine open QTQR, click the Decode button, and select your webcam. Then paint your ONLINE machine webcam at the QR code displayed on the OFFLINE machine and then click Edit on your OFFLINE machine.
15. Copy and paste into the "ONLINE_Procedure.txt" file in the "Add Multisignature Command with Public Keys" section.
16. Repeat steps 14 and 15 to copy over the "Returned Multisignature Address" from the OFFLINE.txt file on the OFFLINE machine to the ONLINE_Procedure.txt file on the ONLINE machine.
17. Print 7 copies of this document (the ONLINE_Procedure.txt).
18. Copy and Paste the "Returned Multisignature Address" into QTQR and click the Save QRCode button and save it to your desktop. Print 7 copies of this QR code and write "Returned Multisignature Address" at the top.
19. Repeat step 18 to print 7 copies of the QR Code for "Add Multisignature Command with Public Keys" section and write "Add Multisignature Command with Public Keys" on the top of each paper.
20. Create 7 stapled packets that contain this procudure (ONLINE_Procedure.txt), the QR code that contains the "Add Multisignature Command with Public Keys" and the QR Code that contains the "Returned Multisignature."
21. Using a blue or black pen write down each of your private keys on each of your packets in the section named "Private Keys." If you have any doubt that your private keys have remained secret and known only to you restart this procedure at step 1. 

--------- current location ---------------

### Test Private Keys
1. On the ONLINE machine use the "importaddress" command with the Mulitisignature Address from the "ONLINE_Procedure.txt."
2. Send a very small amount of bitcoin (less than $5) to this address. You will use this amount to send test transactions of bitcoin from your 7 private keys, but this amount will be permanently lost to reduce the privacy leak involved in spending from your multisignature address.
3. Wait until bitcoin-qt, on the overview screen, shows that the deposit is confirmed.
4. On the OFFLINE machine delete the BitcoinData directory and empty your trash. This will delete your bitcoin private keys.
5. Copy the BitcoinData directory from the OFFLINE machine to the ONLINE machine. 
6. Select 3 random packets and write down "test 1" in the upper right hand corner.
7. On the OFFLINE machine use the "importprivkey" command to import all three private keys.
8. Use the command in the Add Multisignature Command and Public Keys to add the multisignature back to the OFFLINE machine.
9. On the ONLINE machine use the "listunspent" command to grab the "txid," "scriptPubKey," and "vout" and paste this info into a new text document named "testtransaction.txt." 
10. On the ONLINE machine use the command "createwallet donation to hodlers" to create a new wallet.
11. In the upper right hand corner of bitcoin-qt select the "donation to hodlers" wallet and then use the "getnewaddress" command. 
12. Using the "createrawtransaction inputs='''[ { "txid": "'$utxo_txid'", "vout": '$utxo_vout' } ]''' outputs='''{ "'$recipient'": 1.299}''')" command, replace the missing items with the info gathered into the "testtransaction.txt" file. Be sure to make the amount a little less than the amount in the utxo to allow for miner fees. 
13. Using QtQR copy the returned hex number (this is the unsigned transaction) to the OFFLINE machine.
14. On the ONLINE machine, using the signrawtransactionwithwallet command,  sign the transaction and then copy the returned hex number (the signed transaction) to the ONLINE machine using QtQR. 


## Create and backup the Multisig Address
1. On the Offline Laptop create a text file on the desktop named “addresses and redeem script.txt”
2. Generate 7 addresses and copy them into the “addresses and redeem script” text file.
3. Use the “addmultisigaddress” command to create a multisig address. 
4. Copy the 7 addresses, multisig address and the redeem script to the ONLINE laptop using QtQR.
5. On the ONLINE laptop copy and paste the 7 addresses, multisig address and the redeem script into this document and then print 7 copies of it.
6. Print out the QR code for the G addresse, multisig address and the redepmtion script 7 times using QtQR. Using a pen label each QR code.
7. Staple together 7 packets that include the paper copies of this procedure and the QR codes.
6. On the Offline computer find the corresponding private keys from the “dumpprivatekey” command and using a pen add each to the above section in each packet. Be sure and complete the section that specifies the address the corresponds to this private key.l
7. Erase the wallet an the Offline Laptop.
9. On the ONLINE computer Use the “” command to add the multisignature address as a watch only address.
10. Send a small amount of bitcoin to this multisignature address and verify the the funds arrive.

## Restore and Test the Multisig Address

1. On 3 of the paper copies of the document place a “1” in the upper right hand corner (the “1” stands for 1st test).
2. On the Offline machine use the “importprivkey” to import the 3 keys with a “T” into bitcoin core. You will need to take the time to type these in carefully.
3. On the ONLINE machine use the "listunspent" and then transfer the "txid," "scriptPubKey," and "vout" to the Offline computer using the QtQR.3. On the ONLINE machine use the "listunspent" and then transfer the "txid," "scriptPubKey," and "vout" to the Offline computer using the QtQR.3. On the ONLINE machine use the "listunspent" and then transfer the "txid," "scriptPubKey," and "vout" to the Offline computer using the QtQR.



3. On the Offline machine use the “createmultisig” command and the addresses on one of the sheets of paper to restore the multisig address.
4. On the ONLINE machine create a new walled named “donation to hodlers” and create a new address.
5. On the Offline machine  



## Add Multisignature Command with Public Keys

 addmultisigaddress 3
 "[\"first_public_key_here\",\"second_public_key_here\",\"third_public_key_here\",\"fourth_public_key_here\",\"fifth_public_key_here\",\"sixth_public_key_here\",\"seventh_public_key_here\"]"

## Returned Multisignature Address

 Returned_multisig_address_here

## Private Key

This is the private key that corresponds 
to the bitcoin __________ public key above.

The private key is:




1.


2.


3.


4.


5.


6.


7.


8.


9.


10.


11.


12.


13.






It is written using the NATO phonetic alphabet. 
Numbers are written out and letters 
are represented by words where the first letter is the letter of the private key.

Capital letters are indicated by preceding the word with the "#" symbol.

## Repemtion Script
This is the redemption script. 
This can be be recreated by using the bitcoin addresses in the correct order, 
but this script provides rudundancy:

Paste_the_redeem_script_here
