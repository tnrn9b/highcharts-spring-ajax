highcharts-spring-ajax
======================

This is a sample application that shows how to send server-side data to Highchart (http://www.highcharts.com/) in the 
JSON format using a Spring controller. The project is based on maven so upon downloading the project you can do a 
"mvn clean package tomcat7:run" to build and deploy the app to tomcat 7. To access the application open a browser and 
go to "http://localhost:8080/highcharts" There should be 3 charts being displayed. 

The project uses:

Spring 3.2.4.RELEASE (http://www.springsource.org/)
Jackson 1.9.7 (http://jackson.codehaus.org/)
Bootswatch 3.0 (http://bootswatch.com/)
Highcharts 3.0.5 (http://www.highcharts.com/download)
JQuery 1.10.2


Overview:

Upon accessing "http://localhost:8080/highcharts" from the browser a Spring controller "HighChartsController" is called 
and a JSP file called "charts.jsp" is loaded on the browser. Once the loading is complete 3 ajax calls are made back to 
the "HighChartsController" to get the data to display the charts. The "HighChartsController" in turns call a fake
service "ChartService" that generates the fake data for the chats to be generated by Highcharts. The data is stored in   
a java POJO "DataBean" and it is sent back to the controller "HighChartsController". The DataBean is then magically 
converted into a JSON string by Spring. Actually Spring uses Jackson to serialize the DataBean to a string. The string 
is sent back to custom javascript file "custom-chart.js" that has all the plumbing to feed the data to highcharts. 
Highcharts then renders the charts.  


