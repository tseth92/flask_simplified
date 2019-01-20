Above code contains a sample GET and POST call to show the working of Flask API GET call recieves data from a file present in server and POST call saves a file sent to the server.

# Steps to Run Flask Server and trigger GET and POST requests

To Run this code:
1) Just enter command **`python3 flask_simplified.py`**
           This will start the server (Mind it. This is Flask's internal dev server. Don't use it for production)
2) On a different terminal , go inside sourceFiles directory and run the following cURL commands to trigger GET and POST command.
   (GET command can be triggered from anywhere in new terminal but for POST , since we require files, so , it has to be triggered in sourceFiles directory):
	**`curl localhost:5000/getJsonFromFile/labelsFile.txt`**
3) Observe the response recieved. It should give labels_mapping:{"keyvalue pair of labels and numbers}
4) In case the file is not found , you should get error:"error_statement" as the response.
5) Then trigger following cURL command (in sourceFiles Directory)to test POST request :
    **`curl -F "FILES_LIST=@./file1.jpg" -F "FILES_LIST=@./file2.jpg" -F "FILE_NAME=new_file" localhost:5000/uploadFiles`**
	You should get "STATUS":"true" as response and check in directory where flask_simplified.py file is present, the new files should be generated.
	
