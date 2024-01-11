CODE EXPLANATION


Firstly we import the 'requests' library for handling HTTP requests and 'pandas' for efficient data manipulation. We define essential constants, including the ACCESS TOKEN for ThingsBoard API and the corresponding API URL. We use the 'send_data' function to convert a DataFrame into JSON format and send it as a POST request to ThingsBoard, printing the resulting HTTP status code or any encountered errors.

In the 'send_data' function, we define headers for the HTTP request. These headers include 'Content-Type' set to 'application/json' and 'X-Authorization' with a Bearer token constructed using the ACCESS TOKEN. Then we convert the provided DataFrame into a JSON format. We achieve this, first transforming the DataFrame into a dictionary using 'pd.DataFrame.from_dict(dataframe, orient='index')' and converting this dictionary to JSON format using 'to_json(orient='records')'. Inside the 'try' block, we make a POST request to the specified ThingsBoard API URL using the 'requests.post' method. The headers and JSON data are included in the request. The resulting HTTP status code is printed with 'print(f"Status code: {response.status_code}")'. In case of any exceptions during the request, the 'except' block catches the error and prints the specific error message using 'print(f"Error: {str(e)}")'. 


In the 'main' function, we first initialize the main sensor component: a Grove Temperature and Humidity Sensor connected to port D5. The 'DHT' class has the parameters '11' indicating the sensor type (DHT11) and '5' representing the port. We then enter an infinite loop 'while True:', where we read the humidity and temperature values from the sensor using the 'sensor.read()' method. We print these values in the format 'temperature {}C, humidity {}%' using 'print'. We store the temperature and humidity in a dictionary named 'sensor_data'. Then, we call the 'send_data' function, explained in the previous paragraph. Finally, the 'time.sleep(1)' introduces a one-second delay between each iteration of the loop.

Finally, we make sure 'main()' runs when the script is directly started.






OBJECTIVE


Our project objective is to make a simple system for real-time monitoring of temperature and humidity along the Bilbo river. We're working towards creating an easy-to-use, automated solution. Utilizing a Grove Temperature and Humidity Sensor, we collect essential data to understand the local climate. The information we collect can be applied to environmental research, resource management, and for the safety of activities along the river. We provide a clear picture of the Bilbo river's environmental conditions, supporting sustainable practices and informed decision-making for the local community and stakeholders, including Kayaking, Rowing, Paddleboarding.




PROBLEMS DURING THE PROJECT


We had some problems when we were doing the project. The main problem was the slowness of the computer. We had to find a free computer with HDMI input and we had to work with the cell phone's Wi-Fi and the raspberry pi's cmd was very slow.
We have also run out of the free thingsboard mode to be able to analyze the results with graphs. Finally, after many attempts we have not been able to create a website with temperature information.

