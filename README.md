# awulff-pico-playground
RPi Pico Tests &amp; Samples

Instructions from https://www.hackster.io/AlexWulff/adc-sampling-and-fft-on-raspberry-pi-pico-f883dd

All the instructions below are for macOS/Linux, but I imagine there's a similar procedure for CMake on Windows.

To compile my code, first clone my repository on GitHub.

- Navigate to the adc_fft directory
- Make a directory called "build"
- Navigate inside that, and type "cmake../"
- Type "make", and everything should compile if you installed the Pico build system correctly
- Put your Pico into bootloader mode, and then drag and drop the adc_fft.uf2 file into the drive that appears
That should be all! You can monitor the output of the program via USB. It will output the greatest frequency component in data sampled from A0, and the LED should flash rapidly.

Figure out which device the pico USB serial is by typing this commane with and without the pico plugged in:

'ls /dev/tty*'

In my case, the device was /dev/ttyACM0 so I used this command to monitor the serial output:

'sudo apt-get install -y minicom'

'minicom -b 9600 -o -D /dev/ttyACM0'

I extended the code to also print the power level of the maximum frequency:


'Greatest Frequency Component: 9750.0 Hz Power: 5024.843262'                      
'Greatest Frequency Component: 2400.0 Hz Power: 76566.523438'                    
'Greatest Frequency Component: 2400.0 Hz Power: 61474.476562'                     
'Greatest Frequency Component: 23800.0 Hz Power: 4679.298828'                     
'Greatest Frequency Component: 2400.0 Hz Power: 60164.226562'



