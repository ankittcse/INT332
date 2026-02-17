\# Docker Volumes – INT332



This practical covers:

✓ Creating a volume  

✓ Attaching it to containers  

✓ Checking file persistence  

✓ Sharing the volume between containers  

✓ Verifying data after container deletion  



---



\## 1. Create a Docker volume

docker volume create studentdata



\## 2. Run a container and mount the volume

docker run -it --name c1 -v studentdata:/student ubuntu



\## 3. Inside container, create a file

echo "Hello from container c1" > /student/info.txt

cat /student/info.txt



\## 4. Exit container and delete it

exit

docker rm c1



\## 5. Start a new container with same volume

docker run -it --name c2 -v studentdata:/student ubuntu



\## 6. Check if the file still exists (Persistence demo)

cat /student/info.txt



\# Expected:

Hello from container c1



---



\# Sharing Volume Between Multiple Containers



\## 7. Start two containers using same volume

docker run -it --name c3 -v studentdata:/student ubuntu

docker run -it --name c4 -v studentdata:/student ubuntu



\## 8. In container c3, append data

echo "Shared data from c3" >> /student/shared.txt



\## 9. In container c4, read the file

cat /student/shared.txt



\# Expected:

Shared data from c3



---



\# Volume persists even after deleting containers



\## 10. Remove containers but keep volume

docker rm c2 c3 c4



\## 11. Inspect the volume

docker volume inspect studentdata



\# The volume still exists until manually deleted.





