# Alvin Belajar Ajax

How to use this code :
1. Install Nginx (Web Server), PHP (Server language to process web access)
 --> https://techtuts.info/2014/04/install-nginx-php-windows/
2. Setting host  :
   Go to /etc/hosts and write this code :
   ```
   127.0.0.1       alvin.dev
   ```
3. Setting nginx web server for alvin.dev :
   Go to your nginx setting server and write this code
   (my document root is /Users/indraoctama/Sites/alvin , please use your own document root) :
   
   ```
   server {
        root /Users/indraoctama/Sites/alvin;
        index index.html index.htm;

        server_name alvin.dev;

        location / {
                try_files $uri $uri/ /index.html;
        }

        location ~ \.php {
        fastcgi_pass 127.0.0.1:9000;
        fastcgi_index /index.php;

        include fastcgi_params;
        fastcgi_split_path_info       ^(.+\.php)(/.+)$;
        fastcgi_param PATH_INFO       $fastcgi_path_info;
        fastcgi_param PATH_TRANSLATED $document_root$fastcgi_path_info;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
         }  

         location ~ /\.ht {
             deny all;
        }       
     }
     
   ```
4. To view the web on yor local computer then you can go to browser then access : http://alvin.dev . Happy Coding!!

![Alt text](/screenshot/app_screenshot.png?raw=true "Web Screenshot")
   
