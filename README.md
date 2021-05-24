# Pulsar-AGC

<!-- GETTING STARTED -->
## Getting Started

instructions on setting up pulsar in HPC cluser.

### Prerequisites

* python3
 
### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/MetraneAbdelmounim/Pulsar-AGC.git
   ```
2. Change Directory
   ```sh
   cd Pulsar-AGC
   ```
3. Install python's virtual environement
   ```sh
   python3 -m venv venv
   ```
4. Activate python's virtual environement
   ```sh
   . venv/bin/activate
   ```
5. Install pulsar web application
   ```sh
   pip install 'pulsar-app[web]'
   ```
6. Install Pulsar’s required dependencies into the virtual environment 
   ```sh
   pip install -r dev-requirements
   ```
7. Configure Pulsar to monitor a message queue 
   ```sh
   pulsar-config --mq
   ```
8. Additional configration
   ```sh
   cat "app.yml.dev" > "app.yml"
   cat "server.ini.dev" > "server.ini"
   ```
9. Change Path of pulsar directory
   ```sh
   sudo nano app.yml
   ```
   change pulsar path in persistence_directory , staging_directory and tool_dependency_dir attributes

 ### Lauching Pulsar 
  ```sh
   pulsar [--daemon]
   ```
  --daemon argument can be supplied to run Pulsar as a daemon
   ### Pulsar Logs 
  ```sh
   sudo journactl -f -u pulsar.service
   ```
the result should be like this : 

![log_result](https://user-images.githubusercontent.com/48381378/119356694-a12f0500-bc9e-11eb-83d4-35e020f340e6.PNG)
