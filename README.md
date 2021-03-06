# Proof of Authority

Note: Addresses in parentheses are correct, the addresses in the screenshots were taken for the first time I completed the exercise. Scrrenshots were not taken the second time.


##Initial steps
For my initial steps, I installed Geth. Then I went on the create a genesis block. I opened a terminal and launched the puppeth program from Geth. I named my network "hw19poanet" (Note: this is for homework 18, although 19 is in the title). The prompt explains that I am able to easily access the network using a short command of --network=hw19poanet. This is useful because I might need to restart the network in the future.

After installing Geth, I created a new genesis from scratch. The consesus engine will choose Proof of Authority, I used my account number from the Mycrypto app and chose to prefund this account. Prefund this account (0x6e99c8CADf46b085e797B15e7fB05686367b80E3),  (0xd48052623207968F03a3A5C5503876c4A1a6cCDE) and no to precompiling the addresses, Chain-ID= 111.
I exported my genesis configurations to hw19poanet.json, and deleted hw19poanet-harmony.json. I had to copy the hw19poanet.json file into C:ProgramFiles/Git, in order to complete the next step. 
(See screenshot #1 and #1-1)

##Creating Nodes
 Once the new genesis was created, I opened up a new GitBash window to create the two nodes, by entering in "./geth account new --datadir node1" entered a password and wrote down the public address of my node 1 key: (0x6e99c8CADf46b085e797B15e7fB05686367b80E3). I used "./geth account new --datadir node2" to create a second node to recieve another public key:  (0xd48052623207968F03a3A5C5503876c4A1a6cCDE).
(See screenshot #2)


## Launching the nodes to enable mining
  I directed both of the nodes to use the newly created genesis block using this command "./geth datadir node1/2 init yournetworkname.json". I launched the nodes using this command, I copied over the enode: enode://03e3bb67bb71adaf26e987e862fa280b1d03c663e9decce42d01016f4d88c6fe9abd3f3629ab40831fc8aef73fd0d0f67d23311ab7adb388c5e3d3bc94762085@127.0.0.1:30303. Open up another git bash window navigate to your blockchain tools forlder and launch the second node: ./geth --datadir node2 --port 30304 --rpc --bootnodes "enode://<replace with node1 enode address>" --ipcdisable
   
(See screenshot #3 and 3-1)
 
I opened up MyCryptoApp to  create a custom node called 'hw19poanet' and import the node 1 keystore. The keystore was imported but I did not see any funds as I believe the error occured because this account was not initially funded. If I had to do this again I would make sure the account was properly funded.  

(See screenshot #4)
