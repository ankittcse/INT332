\# Environment Variables in Docker – INT332



\## 1. Run a container with an environment variable

docker run -it --name c1 -e COLLEGE=CSE ubuntu



\## 2. Inside container, check variable

echo $COLLEGE



\## 3. Exit container

exit



\## 4. Stop and start container (variable persists)

docker stop c1

docker start c1



\## 5. Exec back into container

docker exec -it c1 bash



\## 6. Check variable again

echo $COLLEGE



\# Why it works?

The variable is stored in container metadata and stays until container is removed.



\# Remove container

docker rm c1



