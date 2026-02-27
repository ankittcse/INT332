&nbsp;Docker Volumes Practical



&nbsp;Commands Used

docker volume create studentdata

docker run -it --name c1 -v studentdata:/mydata ubuntu

echo "Hello" > /mydata/info.txt

docker rm c1

docker run -it --name c2 -v studentdata:/mydata ubuntu

cat /mydata/info.txt



