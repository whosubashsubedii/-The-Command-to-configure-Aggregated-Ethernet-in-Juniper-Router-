

# Configure Aggregated Ethernet (AE) in Juniper Router

This Python script generates Juniper configuration commands to set up a missing Aggregated Ethernet (AE) interface with VPLS (Virtual Private LAN Service).

## 📌 Features

- Accepts user input for:
  - VPLS instance name
  - Aggregated Ethernet (AE) number
  - VLAN ID
- Automatically generates CLI commands in Junos format
- Prints commands ready to be pasted into Juniper CLI

## 🛠 Usage

1. Clone or download the script.
2. Run the script using Python 3:

```bash
python configure_ae_vpls.py
````

3. Enter the required information when prompted:

   * VPLS name
   * AE interface number (e.g., `16` for `ae16`)
   * VLAN ID (e.g., `1120`)

4. Copy the output and use it in Juniper CLI after entering configuration mode.

## 📋 Example Output

```
configure private

set interfaces ae16 unit 1120 description FIBER_220_NET
set interfaces ae16 unit 1120 encapsulation vlan-vpls
set interfaces ae16 unit 1120 vlan-id 1120
set interfaces ae16 unit 1120 family vpls
set routing-instances FIBER_220_NET interface ae16.1120
set routing-instances FIBER_220_NET protocols vpls vpls-id 1120
set routing-instances FIBER_220_NET description "FIBER_220_NET"
set routing-instances FIBER_220_NET instance-type vpls
set routing-instances FIBER_220_NET protocols vpls no-tunnel-services
set routing-instances FIBER_220_NET protocols vpls vpls-id 1120

commit check
```

## 📚 Requirements

* Python 3.x

## 👨‍💼 Author

* SUBASH SUBEDI


