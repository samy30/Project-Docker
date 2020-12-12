# Project-Docker  

this is a simple rest api developed with golang with a mysql database and shipped in docker dontainers.  
  
To run the project you need access to an environment in which are installed **Docker** && **Docker composer**  
  
then run   
**docker stack deploy --compose-file=docker-compose.yml myservice**   
where **myservice** can be changed by the name you wish for the service  
  
that's all you need to run the api and listen at **hostname:8080/products**  
  
(if running at localhost you can copy directly:   **localhost:8080/products**)  
  
possible operations:  
  
**GET  /products**  => list all products  
**GET  /products/productid**  => list product with id **productid**  
**POST  /products**  => post product with the json object **{"title":"choose your title here"}**  
**PUT  /products/productid**  => update product with id **productid** with the json object **{"title":"choose your new title here"}**  
**DELETE  /products/productid**  => delete product with id **productid**  
  
to run **multiple replicas** of this image on **nodes running docker** you have to choose the main host and run the command:  
**docker swarm init**  
  
a command will be prompted containing a token to join the swarm as a distant node threw the specified port     
  
it has the form : **docker swarm join --token hashed_token_provided_by_your_main_host host:port**  
  
than executing the previously mentioned command :  
**docker stack deploy --compose-file=docker-compose.yml myservice**  
will do the magic.  
  
That's all ;) 
