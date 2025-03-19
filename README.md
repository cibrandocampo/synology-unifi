# UniFi Controller on Synology using Container Manager (Docker Compose)

This repository contains a Docker Compose configuration for running the UniFi Controller on a Synology NAS using the Container Manager application. The UniFi Controller is a powerful management and control platform for Ubiquiti network devices.

## Prerequisites

Before proceeding, ensure that you have the following:  

- A Synology NAS with DSM 7.0 or later, properly configured.  
- The **Container Manager** application installed and running.  

## Configuration & Customization

To customize the UniFi Controller settings, edit the `.env` file before importing the project into Container Manager. This allows you to configure environment variables, ports, and other parameters to match your specific requirements.  

## Installation

Follow these steps to deploy the UniFi Controller using Docker Compose:  

1. Copy the `docker-compose.yml` and `.env` files to a folder on your Synology NAS.  
   - You can transfer these files via SSH, the file manager, or any preferred method.  

2. Open the **Container Manager** application from the DSM web interface.  

3. Click **"Import"** to create a new project using Docker Compose.  

4. Navigate to the folder where you copied the `docker-compose.yml` and `.env` files.  

5. Select the `docker-compose.yml` file and click **"Next"**.  

6. Container Manager will automatically detect and load the `.env` file, applying the environment variables.  

7. Review the imported settings and make any necessary adjustments.  

8. Click **"Apply"** to start the deployment of the UniFi Controller container.  

9. Once deployed, access the UniFi Controller web interface by opening a browser and visiting:  
   ```
   http://SYNOLOGY_IP:9001
   ```
   Replace `SYNOLOGY_IP` with the local IP address of your Synology NAS. The port is configurable in the `.env` file.  

10. Follow the UniFi Controller setup wizard to complete the installation.  

## Ensuring a Stable Connection with Access Points

To maintain a stable connection between the UniFi Controller and the WiFi Access Points (APs), follow these steps within the UniFi Controller web interface after installation:

1. Navigate to **Settings** -> **System** -> **Other Configuration**.  
2. Locate the **Override Inform Host** option (near the bottom of the page).  
3. Check the **Enable** box.  
4. Enter the IP address of the Docker host machine.  
5. Save configuration.  
6. Restart the UniFi Controller container.  

Following these steps ensures that the APs can properly communicate with the UniFi Controller.  

**Source:** [Reddit discussion on Synology Docker UniFi Controller](https://www.reddit.com/r/synology/comments/1g2zhz3/synology_docker_unifi_controller_jacobalberty/)  

## Troubleshooting & Contributions

If you encounter any issues or have suggestions for improvements, feel free to contact me at **[hello@cibran.es](mailto:hello@cibran.es)**.  
You can also contribute to this project by submitting pull requests.  

## License

This project is licensed under the [MIT License](LICENSE).  

