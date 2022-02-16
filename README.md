# Pickle-Rick
solved pickle Rick ctf 

   starting with scan ip using nmap -sC -sV 10.10.215.235
   -->
         2 ports found as open
         
         22:ssh
         
         80:http
     
      
  so now search ip in browser we find some conversation like "help me ...." just ignore it cheack it's page source you find username just remember it
  
  now we do hidden directory search using gobuster 
  -->   
        
        gobuster dir -u http://10.10.215.235/ -w /usr/share/wordlists/dirb/common.txt
        
        found some files like robots.txt ,login.php,assert,index.. etc..
        
        just open login.php we need user+password we have user but not password
        
        same open robots.txt got some random string we use it as password.just for try and it's working....wow..
        
        now we have command portal 
        
        ls
        
        we find some file open that file by typing file name at after  url got first indicate (flag)
        
        then for second less command is useful
        
        less '/home/rick/second ingredients' --> it give second flag
        
        sudo less /root/3rd.txt --> it give third flag
        
        happy ending !!!!
