# Secret area
## Reference
https://www.tunnelsup.com/getting-started-cracking-password-hashes/
http://pentestmonkey.net/cheat-sheet/john-the-ripper-hash-formats
http://blog.csdn.net/dongyanwen6036/article/details/77878797
## Steps
1. Reach http://hack.bckdr.in/SECR/index.php?page=secure/.htaccess you will see the password in htpasswd.
2. Open the http://hack.bckdr.in/SECR/index.php?page=secure/.htpasswd you will get the hashed password and user name **vampire:dS/xVY4wI4PRU**
3. use *John-The Ripper* to get the password `john --show hash`
4. you will get the flag now
