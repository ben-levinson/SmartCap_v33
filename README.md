# SmartCap_v33
This application is built from the Zentri BLE Command Android Demo App.

This version includes customized commands:

#Customized Commands
All commands must start with an asterisk (*) and end with a pound sign (#).
Commands (case sensitive):

| First Header | Second Header |
| ------------ | ------------- |
  Content      |  Content      |




# Installation
This project should be imported into Android studio (File -> Import Project).

# Usage
The demo app uses a Service to allow multiple activities to share a BLE connection.  The activities
receive intents from the Service as BLE events occur.

Please refer to the doc directory for javadoc documentation of the Zentri Libaries.
The basic usage of the library is as follows:
```java
mZentriOSBLEManager = new ZentriOSBLEManager();
mZentriOSBLEManager.init(context, mCallbacks);

mZentriOSBLEManager.startScan();

mZentriOSBLEManager.connect("device_name");

mZentriOSBLEManager.GPIOFunctionSet(LED_GPIO, TruconnectGPIOFunction.STDIO);
mZentriOSBLEManager.GPIODirectionSet(LED_GPIO, TruconnectGPIODirection.OUTPUT_LOW);
mZentriOSBLEManager.GPIOSet(14, 1);//set GPIO14 high to turn LED on

mZentriOSBLEManager.adc(10);//read ADC value on GPIO10

```

The above functions add commands into a queue.  The results are accessed through the callbacks
passed into init().

Please see the demo app for an example implementation of the library.

# License
Copyright (C) 2015, Zentri, Inc. All Rights Reserved.

The Zentri BLE Android Libraries and Zentri BLE example applications are provided free of charge
by Zentri. The combined source code, and all derivatives, are licensed by Zentri SOLELY for use
with devices manufactured by Zentri, or devices approved by Zentri.

Use of this software on any other devices or hardware platforms is strictly prohibited.
THIS SOFTWARE IS PROVIDED BY THE AUTHOR AS IS AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING,
BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DIRECT, INDIRECT,
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
