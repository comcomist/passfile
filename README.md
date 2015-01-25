# passFile: Randomizing passwords in a user friendly fashion and in one or more rounds (license: Humanitarian AGPL).
The passFile introduce the additional selected file factor, such that
* the file is first symmetrically encrypted with user password and then
*  hashed to produce the passFile used as the new password. 

This can be done in more than one rounds and by more then one users and also to increase 
asymmetric encrypted communications.

as for what is the hash and encryption functions to be used see http://security.blogoverflow.com/2013/09/about-secure-password-hashing/
while (n>0){ 

    1. PassFile(n) = (isPassFile)?Hash(enc(pbkdf2Sync(PassWord(n)),data(File(n)))): enc(pbkdf2Sync(PassWord(n)),data(File(n))); 
    2. PassFileWord(n)= enc(PassWord(n),PassFile(n)));
        // here we use another user password
    3. PassWord(n-1)=PassFileWord(n);
        // now after using the PassFileWord as PassWord we can repeat the processe with new files and passwords 
    4. n--;
    }
    
  passFile can be used also in communication
	when reviverFile is given to sender in cryptoparty events of singing the pubK of the reviver 
	and passfile=reviverPubk(reviverFile) symkEncrypted=(passfile(Senderfile)) is send from sender  to reviver
	when the password if  pubk as the file is given in cryptoparty with the singing events 

![](http://comcomist.wdfiles.com/local--files/4-new-mediums-in-our-living-the-iiaom-rcoin-comcom-liquid-un/FileWord.png)
