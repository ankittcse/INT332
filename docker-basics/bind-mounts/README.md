\# Docker Bind Mounts – INT332



This practical explains:

✓ Mounting a host directory into a container  

✓ Reading host files inside container  

✓ Writing from container to host  

✓ Verifying data is shared  



---



\# 1. Create a directory on host



mkdir C:\\docker-bind-demo



\# 2. Create a file on host



echo Hello from Host > C:\\docker-bind-demo\\hostfile.txt



\# 3. Run container using bind mount



docker run -it --name bm1 -v C:\\docker-bind-demo:/data ubuntu



\# 4. Inside container, check mounted files



cd /data  

cat hostfile.txt  



\# Expected:

Hello from Host



---



\# 5. Modify file from inside container



echo "Modified inside container" >> /data/hostfile.txt



\# 6. Exit container

exit



\# 7. Verify from host



type C:\\docker-bind-demo\\hostfile.txt



\# Expected:

Hello from Host

Modified inside container



---



\# Why Bind Mounts?

\- Direct access to host files  

\- Good for development  

\- Auto-updates between host and container  

\- Changes persist even after container is deleted  





