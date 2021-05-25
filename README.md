#start build

sudo docker-compose build
sudo docker-compose up

#and then start contrainer consumer and run database.py

sudo docker exec -it 8f6ba5dec8c1 bash
python consumer1.py
python database.py

#test sent data to database in contrainer login

curl -X POST "http://127.0.0.1:5000/post_helloworld" -H "Content-Type: application/json" -d '{"key": "Hello Im palm"}'
