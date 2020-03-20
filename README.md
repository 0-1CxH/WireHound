# WireHound
A Graph-Based Network Monitoring Tool that Works on Large Scale Network.

This is a project of UCR CS179I course, supervised by Prof. Michalis Faloutsos. My teammate is [@Liu](https://github.com/130e).

Backup code source at: https://drive.google.com/drive/folders/12xW9UIQJyXgmw2BWxcxltpuG9lWJVFkp?usp=sharing

## How to Run

```bash
# (Python version = 3.7)
# Install dependencies
pip3 install flask flask-wtf flask-sqlalchemy flask-migrate flask-bootstrap
# Run application
export FLASK_APP=wirehound.py
export FLASK_ENV=development
flask run
```

## Introduction
WireHound is a network monitoring application with a web interface that provides help to network administrators for traffic monitoring and analysis. By analyzing the metric data reported by WireHound, abnormal patterns or signs of attack can be detected. 

In our project, we use the graph-based method of modelling the network traffic, which is a method based on host behavior and flow characteristics, that is, modeling network traffic based on a traffic dispersion graph (TDG) and using it to detect anomalies. The traffic dispersion graph visually shows the social behavior of the hosts in the host community from one aspect. The nodes of the TDG represent hosts, and the edges of the graph represent a certain network traffic pattern. This method of  graph modeling and evaluating using the TDG has much higher reliability than header-based methods and much lower cost than payload-based ones.



## User Journey
- Create an account if user does not have one
- Login to account to access user's private file storage
- Upload traffic files securely
- Choose file to analyze by clicking on filename or delete file by selecting checkbox
- Choose filter options to pick the traffic of interest
- Wait for result
- Use interactive graph on the result to inspect the network
- Take screenshots of the graph (Right-click on the interactive graph)
- Download the json, html and metric data from result page


## Architecture

The product can be divided into two parts: The web application and the data/graph engine. 

Web application:

- Web interface: Based on bootstrap 4.0.Provides a better experience for users.
- Backend routing: Flask for server deployment and routing. Controls the logics of this application in order.
- User account management: Sqlite for database. Manages user accounts.

Data/Graph engine:

- Traffic file parsing and filtering: Dpkt/tshark for file parsing and filtering, which reads and picks the packets of interest from a traffic file.
- Graph visualization: Pyvis for graph visualization, the interactive graph provides an intuitive interface for users to inspect the TDG.
- Data analysis: Networkx for data analysis, which extracts graph metrics for report data. 


## Reference
[1] Iliofotou, Marios, et al. "Network monitoring using traffic dispersion graphs (tdgs)." Proceedings of the 7th ACM SIGCOMM conference on Internet measurement. 2007.

[2] Le, Do Quoc, et al. "Traffic dispersion graph based anomaly detection." Proceedings of the Second Symposium on Information and Communication Technology. 2011.



