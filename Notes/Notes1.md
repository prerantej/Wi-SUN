# Setting Up Wi-SUN Network with Simplicity Studio 🌐

## 1. Project Setup 🛠️

1. **Create and Manage Project:**
   - Use Simplicity Studio to create and manage your project. 💻

2. **Update or Install Components:**
   - Click the "Plus" symbol in the debug menu to update or install necessary components. ➕

## 2. Device Configuration 📦

1. **Connect Devices:**
   - Connect your devices and start them when they are visible. 🔌

2. **Example Project Setup:**
   - Navigate to "Example Projects & Demos."
   - Search for "SOC" while filtering with Wi-SUN. 🔍

## 3. Device Renaming and Configuration 🏷️

### Soc BR Configuration

1. **Rename Device:**
   - Rename your device to "Soc BR" for the Border Router. ✨

2. **Launch Console and Reset:**
   - Launch the console and reset the node. 🔄

3. **Set Wi-SUN Parameters:**
   ```plaintext
   wisun set wisun.network_name "A-IOT_Network"
   wisun set wisun.regulatory_domain IN
   wisun set wisun.chan_plan_id 40
   wisun set wisun.phy_mode_id 5
   ```

4. **Save Configuration and Start:**
   ```plaintext
   wisun save
   wisun start_fan11
   ```

### LFN Device Configuration

1. **Select Device:**
   - Go to "Example Projects & Demos."
   - Filter with Wi-SUN and run the Wi-SUN CLI example. 📋

2. **Connect and Configure:**
   - Connect to the LFN device.
   - Set Wi-SUN parameters similarly:
     ```plaintext
     wisun set wisun.network_name "A-IOT_Network"
     wisun set wisun.regulatory_domain IN
     wisun set wisun.chan_plan_id 40
     wisun set wisun.phy_mode_id 5
     ```

3. **Save and Join Network:**
   ```plaintext
   wisun save
   wisun join_fan11
   ```

## 4. UDP Communication 📡

### Soc BR

1. **Set Up UDP Server:**
   ```plaintext
   wisun udp_server 1234
   ```

### LFN

1. **Set Up UDP Client and Send Messages:**
   ```plaintext
   wisun socket_writeto <socket-id> <BR-IP> 1234 "msg"
   ```

## 5. Using CoAP 🌍

1. **Install CoAP Client on Raspberry Pi:**
   ```bash
   sudo apt install libcoap3 libcoap3-dev
   ```

2. **Send Data Using CoAP:**
   ```bash
   coap-client-notls -m get -N -B 3 coap://[IPv6 address]:5583/info/all
   ```

## 6. GitHub Repos and Software 🐙

1. **Add and Use Repositories:**
   - Add and use repositories from GitHub in Simplicity Studio. 🧩

2. **Wi-SUN Node Monitoring Application:**
   - Add software components as needed.
   - Build and flash the project to the devices. 🚀

## 7. Flashing and Sensor Integration ⚙️

1. **Flashing:**
   - Build and flash the binaries to the devices. 🔥

2. **Sensor Code Integration:**
   - Integrate the sensor code into `app.c`. 📝
