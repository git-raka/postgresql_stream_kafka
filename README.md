# postgresql_stream_kafka


FIRST TIME U MUST HAVE DOCKER AND DOCKER COMPOSE INSTALED IN YOUR OS

nano docker-compose.yml

![image](https://user-images.githubusercontent.com/77326619/158776956-fb02c81e-218e-4164-9c65-8e0a8313b1ab.png)

after it you can run with 
docker-compose up -d

![image](https://user-images.githubusercontent.com/77326619/158777231-1dd1a184-cf5c-4939-8405-86f51d17b9e0.png)

next 

nano debezium.json 
![image](https://user-images.githubusercontent.com/77326619/158777348-98db4ca4-3b62-4052-ab7a-aff96ab86229.png)

curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" 127.0.0.1:8083/connectors/ --data "@debezium.json"
![image](https://user-images.githubusercontent.com/77326619/158777654-d1342e40-5f9b-46d4-8680-f3352252be83.png)


docker run --tty --network raka_default confluentinc/cp-kafkacat kafkacat -b kafka:9092 -C -s key=s -s value=avro -r http://schema-registry:8081 -t postgres.public.ddi

![image](https://user-images.githubusercontent.com/77326619/158777808-5a3de8ae-e011-44b1-b1ed-f8db12ef2f7b.png)
