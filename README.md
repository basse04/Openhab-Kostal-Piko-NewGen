# Openhab-Kostal-Piko-NewGen
# Kostal Inverter Binding Piko  New Generation

Scrapes the web interface of the inverter for the metrics of the supported channels below.

![Kostal Inverter New Generation](doc/kostalinverter8_5.jpg)

## Supported Things

Tested with Kostal Inverter New Generation .


## Discovery

None

## Channels

```
-   gridOutputPower
-   yield_Day
-   yield_Total
-   batStateOfCharge
-   gridVoltageL1
-   gridCurrentL1
-   gridPowerL1
-   gridVoltageL2
-   gridCurrentL2
-   gridPowerL2
-   gridVoltageL3
-   gridCurrentL3
-   gridPowerL3
-   dcPowerPV
-   dc1Voltage
-   dc1Current
-   dc1Power
-   dc2Voltage
-   dc2Current
-   dc2Power
-   dc3Voltage
-   dc3Current
-   dc3Power

-   aktHomeConsumptionSolar
-   aktHomeConsumptionBat
-   aktHomeConsumptionGrid
-   phaseSelHomeConsumpL1
-   phaseSelHomeConsumpL2
-   phaseSelHomeConsumpL3
-   gridFreq
-   gridCosPhi
-   homeConsumption_day
-   ownConsumption_day
-   ownConsRate_day
-   autonomyDegree_day
-   homeConsumption_Total
-   ownConsumption_Total
-   totalOperatingTime
-   current
-   currentDir
-   chargeCycles
-   temperature
-   loginterval
-   s0InPulseCnt

```

## Thing Configuration

demo.things

```
kostalinverterpikonewgen:kostalinverterpikonewgen:inverter [ url="http://'inverter-ip'", refreshInterval=60]

```

If the thing goes online then the connection to the web interface is successful. In case
it is offline you should see an error message.

## Items

demo.items:

```
Number:Power SolarPower         "AC Power [%.2f %unit%]"                        <energy> { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridOutputPower" }
Number:Power SolarPower_Max     "Todays Maximum [%.2f W]"                       <energy> 
Number:Power SolarPower_Min     "Todays Mimimum [%.2f W]"                       <energy>  
Number SolarPowerChart          "Chart Period Solar Power"
DateTime SolarPowerTimestamp    "Last Update AC Power [%1$ta %1$tR]"            <clock>

Number:Energy SolarEnergyDay     "Day Energy [%.2f %unit%]"                     <energy> { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:yield_Day" }
Number:Energy SolarEnergyDay_Max "Todays Maximum [%.2f Wh]"                     <energy>  
Number:Energy SolarEnergyDay_Min "Todays Mimimum [%.2f Wh]"                     <energy>  
Number SolarEnergyDayChart      "Chart Period SolarEnergyDay "
DateTime SolarEnergyDayTimestamp    "Last Update Day Energy  [%1$ta %1$tR]"     <clock>

Number:Energy SolarTotalEnergy         "Total Energy [%.2f %unit%]"             <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:yield_Total" }
Number:Energy SolarTotalEnergy_Max     "Todays Maximum [%.2f kWh]"              <energy>  
Number:Energy SolarTotalEnergy_Min     "Todays Mimimum [%.2f kWh]"              <energy>  
Number SolarTotalEnergyChart    "Chart Period SolarTotalEnergy "
DateTime SolarTotalEnergyTimestamp    "Last Update Total Energy  [%1$ta %1$tR]" <clock>

Number SolarStatus              "Status[%s]"                                    <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:batStateOfCharge" }
Number SolarStatus_Max          "Todays Maximum [%s]"                           <energy>  
Number SolarStatus_Min          "Todays Mimimum [%s]"                           <energy>  
Number SolarStatusChart         "Chart Period SolarStatus "
DateTime SolarStatusTimestamp   "Last Update Solar Status  [%1$ta %1$tR]"       <clock>

Number:ElectricPotential    GridVoltageL1    "L1 Voltage[%.2f %unit%]"          <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridVoltageL1" }
Number:ElectricCurrent      GridCurrentL1    "L1 Current[%.2f %unit%]"          <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridCurrentL1" }
Number:Power                GridPowerL1      "L1 Power[%.2f %unit%]"            <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridPowerL1" }
Number:ElectricPotential    GridVoltageL2    "L2 Voltage[%.2f %unit%]"          <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridVoltageL2" }
Number:ElectricCurrent      GridCurrentL2    "L2 Current[%.2f %unit%]"          <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridCurrentL2" }
Number:Power                GridPowerL2      "L2 Power[%.2f %unit%]"            <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridPowerL2" }
Number:ElectricPotential    GridVoltageL3    "L3 Voltage[%.2f %unit%]"          <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridVoltageL3" }
Number:ElectricCurrent      GridCurrentL3    "L3 Current[%.2f %unit%]"          <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridCurrentL3" }
Number:Power                GridPowerL3      "L3 Power[%.2f %unit%]"            <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridPowerL3" }
Number:Power                DcPvPower        "PV Power[%.2f %unit%]"            <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dcPowerPV" }
Number:ElectricPotential    DC1Voltage       "DC1 Voltage[%.2f %unit%]"         <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc1Voltage" }
Number:ElectricCurrent      DC1Current       "DC1 Current[%.2f %unit%]"         <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc1Current" }
Number:Power                DC1Power         "DC1 Power[%.2f %unit%]"           <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc1Power" }
Number:ElectricPotential    DC2Voltage       "DC2 Voltage[%.2f %unit%]"         <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc2Voltage" }
Number:ElectricCurrent      DC2Current       "DC2 Current[%.2f %unit%]"         <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc2Current" }
Number:Power                DC2Power         "DC2 Power[%.2f %unit%]"           <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc2Power" }
Number:ElectricPotential    DC3Voltage       "DC3 Voltage[%.2f %unit%]"         <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc3Voltage" }
Number:ElectricCurrent      Dc3Current       "DC3 Current[%.2f %unit%]"         <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc3Current" }
Number:Power                DC3Power         "DC3 Power[%.2f %unit%]"           <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:dc3Power" }

Number:Power            AktHomeConsumptionSolar "Home Consumption Solar[%.2f %unit%]"   <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:aktHomeConsumptionSolar" }
Number:Power            AktHomeConsumptionBat   "Home Consumption Battery[%.2f %unit%]" <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:aktHomeConsumptionBat" }
Number:Power            AktHomeConsumptionGrid  "Home Consumption Grid[%.2f %unit%]"    <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:aktHomeConsumptionGrid" }
Number:Power            PhaseSelHomeConsumpL1   "Home Consumption L1[%.2f %unit%]"      <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:phaseSelHomeConsumpL1" }
Number:Power            PhaseSelHomeConsumpL2   "Home Consumption L2[%.2f %unit%]"      <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:phaseSelHomeConsumpL2" }
Number:Power            PhaseSelHomeConsumpL3   "Home Consumption L3[%.2f %unit%]"      <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:phaseSelHomeConsumpL3" }
Number:Frequency        GridFreq                "Grid Frequency[%.2f %unit%]"           <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridFreq" }
Number:Angle            GridCosPhi              "Grid Phase Shift[%.2f %unit%]"         <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:gridCosPhi" }
Number:Energy           HomeConsumption         "Home Consumption Daily[%.2f %unit%]"   <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:homeConsumption_day" }
Number:Energy           OwnConsumption          "Own Consumption Daily[%.2f %unit%]"    <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:ownConsumption_day" }
Number:Dimensionless    OwnConsRate             "Own Cons Rate Daily[%.2f %unit%]"      <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:ownConsRate_day" }
Number:Dimensionless    AutonomyDegree          "Autonomy Degree Daily[%.2f %unit%]"    <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:autonomyDegree_day" }
Number:Energy           HomeConsumption         "Home Consumption Total[%.2f %unit%]"   <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:homeConsumption_Total" }
Number:Energy           OwnConsumption          "Own Consumption Total[%.2f %unit%]"    <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:ownConsumption_Total" }
Number:Time             OperatingTime           "Operating Time Total[%.2f %unit%]"     <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:totalOperatingTime" }
String                  Current                 "Current[%s]"                           <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:current" }
String                  CurrentDir              "Current Dir[%s]"                       <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:currentDir" }
String                  ChargeCycles            "Charge Cycles[%s]"                     <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:chargeCycles" }
Number:Temperature      Temperature             "Temperature[%.2f %unit%]"              <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:temperature" }
Number:Time             Loginterval             "Log Interval[%.2f %unit%]"             <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:loginterval" }
String                  S0InPulseCnt            "S0 In Pulse Counter[%s]"               <energy>  { channel="kostalinverterpikonewgen:kostalinverterpikonewgen:inverter:s0InPulseCnt" }
```
