#Overview: 

API Fortress' DataDog integration is designed to bring your API Fortress test results into DataDog with ease. The process, once set up, is automated. Users can specify either failures only or all test results. Tests that are executed via the scheduler or via external API call will then feed their data into DataDog for visualization.  

#Setup: 

API Fortress' connecter documentation can be found here: http://apifortress.com/doc/setup-connectors/

By setting up a connector and pushing the data to DataDog, all that remains is to assign the imported data (status.success, status.failure) to the desired dashboard and formatting. 

#Metrics: status.success, status.failure, apifortress.latency, apifortress.fetch

#Events: apifortress.events

