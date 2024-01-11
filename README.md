import requests
import pandas as pd
ACCESS TOKEN = "taVTqDu3cXSQwNpOqnxE"
THINGSBOARD_API_URL = "http://thingsboard.cloud/api/vi/taVTqDu3cXSQwNp0qnxE/telemetry"
def send_data(dataframe):
	headers = {
 		'Content-Type': 'application/json',
		'X-Authorization': f'Bearer {ACCESS_TOKEN}'
	}

	# Convert DataFrame to JSON
	# Convert dictionary to Pandas DataFrame
	dataframe = pd.DataFrame.from_dict (dataframe, orient='index') 
	json_data = dataframe.to_json(orient='records')
	try:
		response = requests.post(THINGSBOARD_API_URL, headers-headers, data=json_data) 
		print (f"Status code: {response.status_code}")
	except Exception as e:
		print (f"Error: {str(e)}")


I
#ACESS TOKEN : taVTqDu3cXSQwNp0qnxE
#DEVICE ID : f98201e0-9a67-11ee-80a4-b9287a0d2939
def main():
	# Grove - Temperature&Humidity Sensor connected to port D5 
	sensor = DHT('11', 5)
	while True:
		humi, temp = sensor.read()
		print('temperature {}C, humidity {}%'.format(temp, humi)) 
		sensor_data = {'temperature': temp, 'humidity': humi} 
		send_data(sensor_data)
		time.sleep(1)
if __name__ == '__main__':
	main()
