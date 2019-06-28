# nhandd_docker_django_ubuntu
Dockerfile for django 2.1.8, ubuntu 18.04, python 3.6.8 with python channels, celery, djangorestframework and others (detail in requirements)
In dockerfile, i expose port 80 outside 

# Proxy!
	if your host machine behinds a proxy. add this config for convinience.
	replace <user>:<pass>@<HOST>:<PORT> with your proxy server specifications
	$ sudo vi ~/.docker/config.json
		{
			.....
			<some authentications infomations when you login  here>
			.....
			
			"proxies": {
				"default": {
					"httpProxy": "http://<user>:<pass>@<HOST>:<PORT>",
					"httpsProxy": "http://<user>:<pass>@<HOST>:<PORT>"
					"noProxy": "locahost, 172.*"
				}
			}
		}


# Build container:
	docker build <options> -t <image_name>:<tag> .

# Run image
	# build with volumn mounted, port expose and run into bash
	docker run -v <your_host_machine_path>:<container_path> -p <host_port>:<container_port> -it <image_name> /bin/bash

	
