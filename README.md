# Publishing the first version of mxtheuz.com.br

The first version of your website, which was developed using only HTML. Below, you will find instructions on how to publish the website using the Nginx web server.

## Prerequisites

Before getting started with publishing the website, you will need to have the following installed on your server:

- [Nginx](https://nginx.org/): The web server that will be used to host the site.

## Publishing Instructions

Below are the steps to publish your website using Nginx:

1. **Server Preparation**:
   - Make sure Nginx is installed and configured correctly on your server.
   - Ensure that you have adequate permissions to create and manage files in the directory where the website files will be stored.

2. **File Transfer**:
   - Copy all the website files (HTML files, CSS, images, etc.) to the root directory of the Nginx server. The root directory is usually located at `/var/www/html/` on Linux.

3. **Nginx Configuration**:
   - Access the Nginx server configuration file. Depending on the Linux distribution, the configuration file may be located in different directories, such as `/etc/nginx/nginx.conf` or `/etc/nginx/sites-available/default`.
   - Add a new configuration for your website. You can use a virtual host block for this. Here is an example configuration:

   ```nginx
   server {
       listen 80;
       server_name mxtheuz.com.br;

       root /var/www/html/; # Root directory where the website files are located

       location / {
           try_files $uri $uri/ =404;
       }
   }
   ```

Be sure to replace `mxtheuz.com.br` with your actual domain and root /var/www/html/ with the root directory where the website files are stored.

1. Configuration Testing:

- Before applying the new configuration, check if the Nginx configuration file is correct by running the following command:

```
nginx -t
```

If the output doesn't return any errors, it means the configuration is correct.

2. Applying the Changes:

- After verifying the configuration, restart the Nginx service to apply the changes:

```
sudo systemctl restart nginx
```

3. Accessing the Site:

- Your website should now be publicly accessible at the domain's URL. You can access it in a web browser by typing the corresponding URL.

## Contributing
If you find any issues or have any suggestions to improve the publishing process, feel free to open an issue or submit a pull request.

## License
This project is licensed under the MIT License.

<hr>

Could you follow me? ❤
