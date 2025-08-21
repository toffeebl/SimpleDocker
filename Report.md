# DO5_SimpleDocker Report

## PART 1

1. `sudo apt install docker`
![alt text](Part_1/docker_instal.png)

    `docker pull nginx`
![alt text](Part_1/part1.1.png)

2. `docker images`
![alt text](Part_1/part1.2.png)

3. `docker run -d (container_ID)`
![alt text](Part_1/part1.3.png)

4. `docker ps` (ps-"Process Status)
![alt text](Part_1/part1.4.png)

5. The info on the container:

 i. IP=172.17.02 (`docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' hungry_shannon`)
       ![alt text](Part_1/part1.5_incpect_ip.png)

ii. SIZE=1095 bytes (`docker inspect --size -f 'RW = {{ .SizeRw }}; ROOTFS = {{ .  SizeRootFs }}' hungry_shannon`)

  ![alt text](Part_1/part1.5_inspect_size.png)

 iii. List of mapped ports (`docker inspect --type=container -f '{{.NetworkSettings.Ports}}' hungry_shannon`)
       ![alt text](Part_1/part1.5_inspect_ports.png)

6. `docker stop`
![alt text](Part_1/port1.6_stop.png)

7. `docker ps`

    ![alt text](Part_1/part1.7.png)

8. `docker run -d -p 80:80 -p 443:443 nginx`
![alt text](Part_1/part1.8.png)

9. `curl localhost:80`
![alt text](Part_1/part1.9.png)

10. Nginx is restarted and works well
![alt text](Part_1/part1.10.png)

## PART 2

1. `docker exec` command

     ![alt text](Part_2/part2.1.png)

2. Copying the basic config file, pasting it in a local config file (see **part2/nginx_origin.conf**) and then enrich it with the \[local\] server configuration. Please refer to the **./part2/nginx.conf** file for details. This file should replace the NGINX configuration in the container. When it is done, reloading the server  
![alt text](Part_2/part2.2.png)

3. Reloading (`docker exec container_name nginx -s reload`) and checking the **localhost:80/status** (`curl localhost:80/status`):  

  ![alt text](Part_2/part2.3_reload.png)

4. Exporting the container into a **.tar** archive

![alt text](Part_2/part2.4.png)

5. Stopping containers, removing images and containers - cleansing routine.

![alt text](Part_2/part2.5.png)

![alt text](Part_2/part2.5_2.png)

6. Importing with `docker import -c 'CMD ["nginx", "-g", "daemon off;"]' ./serene_babbage.tar re_nginx` and launching the image via `docker run --rm -d -p 80:80 -p 443:443 --name toffee re-nginx`:

![alt text](Part_2/part2.6.png) 

## PART 3

1. Cleaning up the ground
![alt text](Part_3/part3.1.png)

2.![alt text](Part_3/part3.2.png)

3.![alt text](Part_3/part3.3.png)

4.![alt text](Part_3/part3.4.png)

5.![alt text](Part_3/part3.5.png)

6.![alt text](Part_3/part3.6.png)

7.![alt text](Part_3/part3.7.png)

8.![alt text](Part_3/part3.8.png)

9.![alt text](Part_3/part3.9.png)

## PART 4

1.![alt text](Part_4/part4.1.png)

2.![alt text](Part_4/part4.2.png)

3.![alt text](Part_4/part4.3.png)

4.![alt text](Part_4/part4.4.png)

5.![alt text](Part_4/part4.5.png)

6.![alt text](Part_4/part4.6.png)

## PART 5

1.![alt text](Part_5/part5.1.png)

2.![alt text](Part_5/part5.2.png)

3.![alt text](Part_5/part5.3.png)

## PART 6

1.![alt text](Part_6/part6.1.png)

2.![alt text](Part_6/part6.2.png)

3.![alt text](Part_6/part6.3.png)

4.![alt text](Part_6/part6.4.png)

5.![alt text](Part_6/part6.5.png)

6.![alt text](Part_6/part6.6.png)