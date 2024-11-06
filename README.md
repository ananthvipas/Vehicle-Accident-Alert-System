# Vehicle-Accident-Alert-System.
we are going to build a Arduino based vehicle accident alert system using GPS, GSM and accelerometer. Accelerometer detects the sudden change in the axes of vehicle and GSM module sends the alert message on your Mobile Phone with the location of the accident.

Includes and Definitions

    #include <SoftwareSerial.h>
    SoftwareSerial Serial1(2,3); // RX = pin 2, TX = pin 3
    SoftwareSerial gps(10,11);   // RX = pin 10, TX = pin 11
    #define x A1
    #define y A2
    #define z A3

    int xsample=0;
    int ysample=0;
    int zsample=0;

    #define samples 10
    #define minVal -50
    #define MaxVal 50

This part includes the necessary libraries and defines pins and variables.
SoftwareSerial is used to communicate with devices using software (bit-banging) serial communication, allowing multiple serial devices to communicate with a single hardware UART (Universal Asynchronous Receiver-Transmitter) port.
Serial1 is initialized to communicate with a device connected to Arduino pins 2 and 3.
gps is initialized to communicate with a GPS module connected to Arduino pins 10 and 11.
Pins A1, A2, and A3 are defined for analog input.
Variables xsample, ysample, and zsample are initialized for storing sensor readings.
samples defines the number of samples to be averaged.
minVal and MaxVal set the minimum and maximum values for sensor readings.

Function Definitions

    void initModule(String cmd, char *res, int t) { /* Function code */ }

    void setup() { /* Setup code */ }
    void loop() { /* Loop code */ }
    void gpsEvent() { /* GPS event handling code */ }
    void get_gps() { /* GPS data retrieval code */ }
    void show_coordinate() { /* Display GPS coordinates and speed */ }
    void coordinate2dec() { /* Convert GPS coordinates from degrees and minutes to decimal format */ }
    void Send() { /* Send GPS data via SMS */ }
    void serialPrint() { /* Print data received via Serial1 */ }

    These are function declarations. The actual implementation of each function follows later in the code.

Setup Function


    void setup() {
      Serial1.begin(9600);
      Serial.begin(9600);
      /* Initialization code */
    }

setup() is a special function that runs once when the Arduino is powered on or reset.
It initializes serial communication with baud rate 9600 for both Serial1 and the hardware UART (Serial).

Loop Function


    void loop() {
      /* Main loop code */
    }

loop() is another special function that runs repeatedly after setup() has completed.
It contains the main logic of the program, including reading sensor values, checking conditions, and sending data.

Other Functions

initModule(): Initializes communication with a module by sending AT commands and waiting for a response.
gpsEvent(): Handles incoming GPS data, extracts relevant information, and sets the GPS status flag.
get_gps(): Retrieves GPS data by calling gpsEvent() and converting coordinates to decimal format.
show_coordinate(): Displays latitude, longitude, and speed information received from the GPS module.
coordinate2dec(): Converts latitude and longitude from degrees and minutes to decimal format.
Send(): Sends GPS data via SMS using AT commands through Serial1.
serialPrint(): Prints data received via Serial1 (used for debugging).
