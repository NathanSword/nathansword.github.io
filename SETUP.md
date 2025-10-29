1. I first created an account and instance with a public ip on oracle cloud
2. After obtaining the keys I used ssh to enter the instance where I loaded updates using the steps provided by the help channel in teams:
    1) sudo fallocate -l (that's an L) 8G /swapfile
    2) sudo chmod 600 /swapfile
    3) sudo mkswap /swapfile
    4) sudo swapon /swapfile
    5) vi /etc/fstab (to check if swapfile is there, below everything you can type in :wq (save/quit) or :q! (force quit), then press enter to exit it)
    6) free -h or free -m to check to see if you have it working as well
    7) sudo systemctl daemon-reload
    8) sudo yum update -y
3. Then using the steps from the provided node express video I installed node express and setup an index.js:
   https://www.youtube.com/watch?v=AL7_oPEigpM
4. In the index.js I pasted in the code provided and after creating new ingress rules in the security list of instance settings enabling both port 3000 and 80 to be an exception
5. After all of those steps I was able to open the instance methods on my browser with the url="http://129.153.226.27:3000/echo" and after using nano index.html to input the html code I was able to open the main webpage with the url="http://129.153.226.27:3000". I am able to get there by using the following commands in powershell:
    1) cd key_file
    2) ssh -i .\ssh-key-2025-10-06.key opc@129.153.226.27
    3) cd my_node
    4) node index.js (Turns on the website)
    5) http://129.153.226.27:3000/echo (for request methods)
    6) http://129.153.226.27:3000 (for html)
7. Because I already had a git repo already under my user I decided to just use that and I made an index.html under main with the given code that redirects you to the main website.

