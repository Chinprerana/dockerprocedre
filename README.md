⚙️ Procedure
1. Pull NGINX Image
docker pull nginx
2. Run Container with Port Mapping
docker run -d -p 8085:80 nginx

Open in browser: http://localhost:8085

3. Create Docker Volume
docker volume create my-volume
docker volume ls
4. Run Container with Volume
docker run -d -p 8087:80 -v my-volume:/usr/share/nginx/html nginx
5. Verify Container
docker ps
6. Create File in Container
docker exec -it <container_id> sh
echo "Hello Persistent Storage!" > /usr/share/nginx/html/index.html
exit
7. Check Output

Open: http://localhost:8087

Output: Hello Persistent Storage!

8. Test Persistence
docker stop <container_id>
docker rm <container_id>
docker run -d -p 8087:80 -v my-volume:/usr/share/nginx/html nginx

Open again: http://localhost:8087
