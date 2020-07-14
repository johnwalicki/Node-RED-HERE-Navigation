# Node-RED HERE Navigation Routing Dashboard
HERE Navigation Routing API Example on a Node-RED Dashboard

Use the [HERE.com Routing APIs](https://developer.here.com/documentation#routing_and_navigation_section) to build a map navigation dashboard and plot the route on a [Node-RED](https://nodered.org) Dashboard.  Use the [Watson Text to Speech](https://cloud.ibm.com/docs/text-to-speech?topic=text-to-speech-about#about) service to narrate the route.

This example flow and Node-RED Dashboard might be useful as part of a [Call for Code](https://developer.ibm.com/callforcode/) solution that uses HERE Technologies APIs.  Natural disaster applications could guide someone to safety.

### Prerequistes

- [Install Node-RED](https://nodered.org/docs/getting-started/) on your system or in the cloud
  - This flow can be deployed to [IBM Cloud](https://cloud.ibm.com/registration) by creating a [Node-RED Starter Application](https://developer.ibm.com/components/node-red/tutorials/how-to-create-a-node-red-starter-application/)
- This flow requires Node-RED v1.1 or higher
- [Add the following nodes](https://nodered.org/docs/user-guide/runtime/adding-nodes) to your Node-RED palette
  - [node-red-dashboard](https://flows.nodered.org/node/node-red-dashboard)
  - [node-red-node-ui-table](https://flows.nodered.org/node/node-red-node-ui-table)
  - [node-red-contrib-web-worldmap](https://flows.nodered.org/node/node-red-contrib-web-worldmap)
  - [node-red-node-watson](https://flows.nodered.org/node/node-red-node-watson)
- Signup for a [HERE Developer account](https://developer.here.com)
- Signup for an [IBM Cloud](https://cloud.ibm.com/registration) account
- Create a (free) instance of [Watson Text to Speech](https://cloud.ibm.com/catalog/services/text-to-speech)

## Node-RED flow in this repository:
---
### A flow that displays a Navigation Route on a map

![HERE Navigation Dashboard](screenshots/Node-RED-HERE-Navigation-dashboard.png?raw=true "HERE Navigation Dashboard")
<p align="center">
  <strong>Get the Code: <a href="flows/here.json">Node-RED flow for HERE Routing / Navigation</strong></a>
</p>

![Severe Weather Alert flow](screenshots/Node-RED-HERE-Navigation-flow.png?raw=true "HERE Navigation flow")

This flow has four sections:
1. The **Starting and Destination Locations / Geocode** section displays a Node-RED Dashboard form which prompts the navigator
to enter their starting location and ending destination.  The flow then calls the [HERE Geocode Search API](https://developer.here.com/documentation/geocoding-search-api/dev_guide/index.html) to determine the latitude and longitude of the two waypoints.
1. The **Request Driving Navigation Instructions** section calls the [HERE Routing API](https://developer.here.com/documentation/routing/dev_guide/topics/introduction.html) to calculate the route between the two locations.  It builds a table of these driving instructions and displays a summary of the route distance and driving duration.
1. The **Draw Map and Route** section moves the car on the node-red-contrib-web-worldmap as the navigator clicks on the **Navigation Preview** button.
1. The **Read the Driving Instructions** section determines if the mute slider is on / off and uses the Watson Text to Speech service to read the driving instructions aloud. Paste your Watson Text to Speech credentials into the node.
---

### Authors

- [John Walicki](https://github.com/johnwalicki)

___

Enjoy!  Give us [feedback](https://github.com/johnwalicki/Node-RED-HERE-Navigation/issues) if you have suggestions on how to improve this tutorial.

## License

This tutorial is licensed under the Apache Software License, Version 2.  Separate third party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1 (DCO)](https://developercertificate.org/) and the [Apache Software License, Version 2](http://www.apache.org/licenses/LICENSE-2.0.txt).
