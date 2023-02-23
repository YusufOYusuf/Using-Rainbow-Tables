<h1>Using Rainbow Tables</h1>


<h2>Description</h2>
In this lab, I learned to use rainbow tables. A rainbow table is used to create a table file, sort it, and use it to brute force an encrypted md5 hash. It is a pre-computed table for reversing cryptographic hash functions, usually for cracking password hashes.
<br />



<h2>Environments Used </h2>

- <b>Windows Server 2016 Datacenter</b> 

<h2>Utilities and Language </h2>

- <b>Powershell</b>

<h2>Program walk-through:</h2>

<p align="center">
Click on the start menu and navigate to windows powershell<br/>
<img src="https://i.postimg.cc/yxNPmFdj/Screen-Shot-2023-02-23-at-2-54-51-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
  
<br />
Insert the following commands to create a rainbow table and sort it <br>
<br>cd C:\Lab_Files\rainbowcrack-1.7-win64\ 
<br>.\rtgen.exe md5 loweralpha 1 3 0 1000 1000 0
<br>.\rtsort.exe .<br>
<img src="https://i.postimg.cc/5NgmPKv3/Screen-Shot-2023-02-23-at-3-01-23-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
Now execute the following commands to encrypt a message in the MD5 hash <br>
cat Encrypt.txt <br>
md5sums -e Encrypt.txt <br>
<img src="https://i.postimg.cc/Cxd6bptD/Screen-Shot-2023-02-23-at-3-05-48-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
In the Windows powershell window type in the following command to brute force the encrypted hash using the above created rainbow table <br>
.\rcrack.exe . -h <MD5 sum noted in step 4> <br>
You can now observe the encrypted MD5 hash and decrypted message <br>
<img src="https://i.postimg.cc/JhbrCF8y/Screen-Shot-2023-02-23-at-3-11-46-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





