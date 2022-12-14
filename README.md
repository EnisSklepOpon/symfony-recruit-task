# Back-End Developer Task - Supplier Stock Processing

**A small, Symfony-based project checking your backend development skills.** 


### Requirements/prerequisites:
* Symfony 6.x, Doctrine, MySQL/Postgresql
* Docker environment
* Unit and functional test


### Task description
Create a Symfony app with a REST API returning JSON containing stock information.

1. Create docker-compose based development environment (you can use webdeveops/php-nginx-dev image)
2. Create command consuming csv files and importing its data to database
    * command should have two arguments: absolute filepath and supplier name
    * every supplier might have different file format (take this into account)
    * ideally every supplier should have his own processor/transformer
3. Create unit tests for classes responsible for transforming csv file records into entities.
4. On our stock item entity we would like to store information:
    * EAN (or null if not present)
    * MPN (manufacturer producer number)
    * Producer name
    * External id
    * Price
    * Quantity
5. Prepare *anonymous* API with one endpoint:

    a) /get-stocks endpoint
   
    * with two query attributes:     
      1. mpn
      2. ean
    
        where at least one must be specified in order to return any results.
    * respectively return results based on filtering by mpn or ean field.
    * result should contain all data available for each stock item

6. Create functional test of created api endpoint (using phpunit + symfony WebTestCase), ideally using zenstruck/foundry for fixtures but its not a must.

Inside *data* directory there are two files from different suppliers with some additional information about how to parse them.

**Once completed, submit to any public git repository and provide us with link.**