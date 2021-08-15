Using the application from your own machine with localhost
----------------------------------------------------------

When you want to test the application using an emulator with the real API using localhost, you'll need to follow a couple of steps to get things running. By default, localhost on your machine won't be accessible from the emulator (Android or iOS). Please note that several solutions exist to work around this problem, the below solution is describing the way I work.

1. Download SharpProxy from https://github.com/jocull/SharpProxy
2. Open the Xamarin solution. In there, rightclick on the API (BethanysPieShop.API) and select Debug -> Start new instance. The API will launch. Take note of the port number it's running on.
3. Run the SharpProxy project and enter the port number on which your ASP.NET Core API is running in the Internal port field. 
4. Take the IP address (also shown in SharpProxy) + the external port number and now go to the Xamarin project. Search for the ApiConstants class and in there, you'll find the IP I've used (192.168.1.35:5000). Replace that with the IP + port number for your machine (shown in SharpProxy).
5. With the API and SharpProxy now still running, you can now launch your Xamarin.Android or Xamarin.iOS project. From Visual Studio, again rightclick and select Debug --> Start new instance.

Your Xamarin application should now be able to access the API. 
Alternatively, you can also host the API in for example an Azure Web App.

Swagger:
--------
http://localhost:20650/swagger/index.html
http://localhost:20650/swagger/v1/swagger.json
 
http://10.0.0.22:5000/swagger/index.html