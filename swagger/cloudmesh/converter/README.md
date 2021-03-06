# Reproducible Rest Service with Swagger 

## Acknowlegement: 
I cloned the repo owned by Guo, Yue (hid-sp18-508) and learnt about the make 
file before I modified and created my own make file for this assignment

## About REST Service
This REST service is a computational tool (application) that convert the number between the binary and decimal. Without using any database, the tool could convert any number from binary to decimal, and vice versa.

## Notes For Instructors 
This is the directory for REST Service with Swagger. 

* The reproducibility can be achieved by using the Make file:
    - make clean -- removes the code generated

    - make service -- creates the swagger service from the yaml file 
    and places the default_controller.py in the controller directory

    - make start  -- starts the service

    - make stop -- stops the service

    - make all -- creates and starts the service
    
    - make container -- creates a docker container that runs the service

* The yaml file I used is in 

        hid-sp18-524/swagger/cloudmesh/converter/converter.yaml
    
* The default_controller is at 

        hid-sp18-524/swagger/cloudmesh/converter/default_controller.py
  


## Server Generation Using Swagger Codegen

I followed the instruction from chapter 34: REST Service Generation with Swagger. 

## Start The Server

* Clone the repository
* Navigate to the directory 

        cd /hid-sp18-524/swagger/cloudmesh/converter
        
* Creates the swagger service from the yaml file with correct controllers
        
        make service
        
* Start the service by execute:

        make start

* The following will show

        Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
        
## Test The Server
* Add the base path after the http://0.0.0.0:8080/ with a binary or decimal number. For example, if you want to convert a binary number to a decimal: http://0.0.0.0:8080/api/to-decimal/101 (a binary number).

Same for converting the decimal to binary: http://0.0.0.0:8080/api/to-binary/5 (a decimal number).

## Additional
* If you use swagger codegen to reproduce the server, you might run into a situation that the default_controller.py becomes empty. Please use the default_controller.py in the repo to refill the code if you run into this situation.

## Stop The Server

* Stop the service by:

        make stop
        
* removes the code and directories generated:

        make clean
