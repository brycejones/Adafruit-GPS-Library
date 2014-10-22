
*************************************************************
Fork implementing ability to query and report on antenna status 
per GlobalTop's FGPMMOPA6H Data Sheet Rev: V0A employing the
use of their defined Antenna Status Protocol (Antenna Advisor
Protocol support [$PGTOP]  brycej

*************************************************************
Example Arduino sketch additions using newly supported Antenna Supported Protocol method: 

      Serial.print("Angle: "); Serial.println(GPS.angle);
      Serial.print("Altitude: "); Serial.println(GPS.altitude);
      Serial.print("Satellites: "); Serial.println((int)GPS.satellites);
      Serial.print("Antenna Status: "); Serial.print(GPS.antennastatus, DEC);  //print antenna status
  
      switch ( GPS.antennastatus ) {
           case 1:
              Serial.print(" -Antenna Shorted!!\n");        // Fault with Antenna
           break;
           case 2:
              Serial.print(" -Using Internal Antenna\n");   // GPS using internal ceramic antenna
           break;
           case 3:
              Serial.print(" -Using Active Antenna\n");     // GPS using active antenna
           break;
           
           default:
           // Get out of here
           break;
           }


|||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||
EXAMPLE CONSOLE OUTPUT: (location obscured)

Time: 18:55:50.0
Date: 2/26/2014
Fix: 1 quality: 2
Location: 38**.9091N, 94**.3886W
Speed (mph): 0.01
Angle: 304.97
Altitude: 314.00
Satellites: 9
Antenna Status: 3 -Using Active Antenna

$PGTOP,11,3*6F
$GPGGA,185551.000,38__.9093,N,094__.3888,W,2,9,1.01,314.0,M,-30.2,M,0000,0000*66
$GPRMC,185551.000,A,38__.9093,N,094__.3888,W,0.02,304.97,260214,,,D*79



<fini>
*************************************************************
*************************************************************
*************************************************************
*************************************************************
*************************************************************

This is the Adafruit GPS library - the ultimate GPS library
for the ultimate GPS module!

Tested and works great with the Adafruit Ultimate GPS module
using MTK33x9 chipset
    ------> http://www.adafruit.com/products/746

These modules use TTL serial to communicate, 2 pins are required to  
interface

Adafruit invests time and resources providing this open source code, 
please support Adafruit and open-source hardware by purchasing 
products from Adafruit!

Written by Limor Fried/Ladyada  for Adafruit Industries.  
BSD license, check license.txt for more information
All text above must be included in any redistribution

To download. click the "Download ZIP" at the right side, extract the archive and rename the uncompressed folder Adafruit_GPS. Check that the Adafruit_GPS folder contains Adafruit_GPS.cpp and Adafruit_GPS.h

Place the Adafruit_GPS library folder your <arduinosketchfolder>/libraries/ folder. You may need to create the libraries subfolder if its your first library. Restart the IDE.
