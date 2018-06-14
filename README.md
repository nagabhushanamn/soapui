# soapui

---------------------------------------------------------------------------------

 e.g shopping-application  ( shopping-system.jpg )

    e.g shop services   

        - products service
        - order services
        ....

---------------------------------------------------------------------------------

designing REST - API

1. Resource identification in requests

    resources

    - Product       ==> /products
    - Review        ==> /reviews
    ....
    relationshop b/w resources e.g 1 product can have many resources

                    ==> /products/{id}/reviews

2. Resource manipulation through representations     
       
    
    representations => html, xml, json, pdf, xls, csv, ...


3. Self-descriptive messages

    headers e.g  ==> Content-Type, Headers

4. Hypermedia as the engine of application state (HATEOAS)


---------------------------------------------------------------------------------        

real implementations

    1. data-source   ==> SQL, NoSQL, file, ....

    2. service-application     ==> Langugae  + Language-Platform

                                  e.g Java/JavaScript   + JRE/Node.js


--------------------------------------------------------------------------------- 

 e.g shopping application

 steps to run sample 'shop-api' application

  => install node.js runtime : https://nodejs.org/en/
    
verify Node.js runtime

  > node -v
  > npm -v

  on project directory

  > npm i    
  > npm start

  ---------------------------------------------------





