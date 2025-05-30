# SMA-Modbus-energy-management-system
EMS in Home Assisant and Node-RED

I’ve created an Energy Management System (EMS) using Node-RED, running as an add-on in Home Assistant.

Goal:
The goal of this EMS is to make my classic SMA inverter smarter. I want to take advantage of favorable electricity prices and avoid negative situations using hourly dynamic pricing.

I started this in 2022, when I installed my solar panels:

12 panels (405W) facing South-East

10 panels (405W) facing South-West

Inverter: SMA Tripower 8 SE

Battery: BYD

Energy meter: SMA Home Manager 2

⚠️ Important Notice:
I removed the SMA Home Manager 2 from Sunny Portal and only use Home Assistant to control my system.
Since the latest firmware update, Modbus register 41255 (used for curtailment control) gets overwritten by the Home Manager 2.
SMA is preparing their own EMS (expected Q3 2025), so they changed how the Home Manager interacts with the inverter.

To regain full control over Modbus, I unlinked the Home Manager 2 from Sunny Portal.
It now acts like a standard energy meter. It still controls the battery’s basic behavior, but I have full access to all registers again.
If you use a classic SMA Energy Meter (not Home Manager 2), this limitation does not apply.

Features in this Release 1.0:
    
    1. Zero export when export price is negative → Only generate energy used in the house.

    2. Negative import prices → Charge the battery during the 3 most negative price hours (still in test phase).

    3. Smart selling → Sell excess energy at peak prices in the morning/evening, if solar forecast is strong (March–September).

    4. Delayed battery charging → Wait until export prices are lowest.

    5. Winterflow → Charge battery during the 4 cheapest hours at night if solar forecast <15 kWh and price spread is significant.

    6. Dunkelflaute mode → Use battery during hours when import prices are above a defined threshold.

🛠️ Note:
Feel free to use or modify my flows for your own setup. You do so at your own risk.

<img width="1051" alt="image" src="https://github.com/user-attachments/assets/3dcc6b91-a6b7-453f-8a19-410d1f3061a3" />

<img width="993" alt="image" src="https://github.com/user-attachments/assets/8b72d425-1f3d-4b6b-9fc8-65d8495aefa0" />

The file "ALL IN ONE . JSON" contains al the flows in the pictures below. You can import them in Node-RED. 

<img width="710" alt="image" src="https://github.com/user-attachments/assets/7757c1ec-6be6-4901-a245-476732700c47" />

<img width="1708" alt="image" src="https://github.com/user-attachments/assets/7bb14797-705e-44bb-8b82-ad97170af8c0" />

<img width="1506" alt="image" src="https://github.com/user-attachments/assets/30601cb8-5a07-41e5-a8d7-a372f6541ad5" />

<img width="1675" alt="image" src="https://github.com/user-attachments/assets/42cc0725-ea89-499f-a1fe-733d622cff18" />

<img width="1483" alt="image" src="https://github.com/user-attachments/assets/669d6f3c-d366-454e-90d9-9418013f31e3" />

<img width="1526" alt="image" src="https://github.com/user-attachments/assets/7e187848-4cfc-46bc-83fe-bed33e142076" />




