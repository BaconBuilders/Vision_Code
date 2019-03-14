===================
Building on desktop
===================

--------
Building
--------

Java 11 is required to build.  Set your path and/or JAVA_HOME environment
variable appropriately.

1) Run "./gradlew build"

---------
Deploying
---------

On the rPi web dashboard:

1) Make the rPi writable by selecting the "Writable" tab
2) In the rPi web dashboard Application tab, select the "Uploaded Java jar"
   option for Application
3) Click "Browse..." and select the "java-multiCameraServer-all.jar" file in
   your desktop project directory in the build/libs subdirectory
4) Click Save

The application will be automatically started.  Console output can be seen by
enabling console output in the Vision Status tab.

=======================
Building locally on rPi
=======================

1) Run "./gradlew build"
2) Run "./install.sh" (replaces /home/pi/runCamera)
3) Run "./runInteractive" in /home/pi or "sudo svc -t /service/camera" to
   restart service.



68-91 Center Band




//Code Archive

                  // write a formatted string to the serial transmit buffer
                  serial.write("CURRENT TIME: " + new Date().toString());

                  // write a individual bytes to the serial transmit buffer
                  //serial.write((byte) 13);
                  //serial.write((byte) 10);

                  // write a simple string to the serial transmit buffer
                  serial.write("500");

                  // write a individual characters to the serial transmit buffer
                  // serial.write('\r');
                  serial.write('\n');

                  // write a string terminating with CR+LF to the serial transmit buffer


/****Original Pipeline***/                 
                 
 public void process(Mat source0) {
		// Step HSL_Threshold0:
		Mat hslThresholdInput = source0;
		double[] hslThresholdHue = {59.89208633093525, 110.30303030303028}; 
		double[] hslThresholdSaturation = {151.34892086330933, 255.0};
		double[] hslThresholdLuminance = {50.44964028776984, 255.0};
		hslThreshold(hslThresholdInput, hslThresholdHue, hslThresholdSaturation, hslThresholdLuminance, hslThresholdOutput);

		// Step CV_erode0:
		Mat cvErodeSrc = hslThresholdOutput;
		Mat cvErodeKernel = new Mat();
		Point cvErodeAnchor = new Point(-1, -1);
		double cvErodeIterations = 2.0;
		int cvErodeBordertype = Core.BORDER_CONSTANT;
		Scalar cvErodeBordervalue = new Scalar(-1);
		cvErode(cvErodeSrc, cvErodeKernel, cvErodeAnchor, cvErodeIterations, cvErodeBordertype, cvErodeBordervalue, cvErodeOutput);

		// Step Find_Contours0:
		Mat findContoursInput = cvErodeOutput;
		boolean findContoursExternalOnly = false;
		findContours(findContoursInput, findContoursExternalOnly, findContoursOutput);

		// Step Filter_Contours0:
		ArrayList<MatOfPoint> filterContoursContours = findContoursOutput;
		double filterContoursMinArea = 125.0;
		double filterContoursMinPerimeter = 0.0;
		double filterContoursMinWidth = 35.0;
		double filterContoursMaxWidth = 50.0;
		double filterContoursMinHeight = 100.0;
		double filterContoursMaxHeight = 1200.0;
		double[] filterContoursSolidity = {0.0, 100.0};
		double filterContoursMaxVertices = 1000000.0;
		double filterContoursMinVertices = 0.0;
		double filterContoursMinRatio = 0.0;
		double filterContoursMaxRatio = 1000.0;
		filterContours(filterContoursContours, filterContoursMinArea, filterContoursMinPerimeter, filterContoursMinWidth, filterContoursMaxWidth, filterContoursMinHeight, filterContoursMaxHeight, filterContoursSolidity, filterContoursMaxVertices, filterContoursMinVertices, filterContoursMinRatio, filterContoursMaxRatio, filterContoursOutput);


    assign(filterContoursContours);   //filterContoursContours
	}



/*New Pipeline for brighter*/


			// Step HSL_Threshold0:
		Mat hslThresholdInput = source0;
		double[] hslThresholdHue = {40.46762589928058, 49.69696969696968};
		double[] hslThresholdSaturation = {48.156474820143885, 76.93570932881188};
		double[] hslThresholdLuminance = {220.14388489208633, 255.0};
		hslThreshold(hslThresholdInput, hslThresholdHue, hslThresholdSaturation, hslThresholdLuminance, hslThresholdOutput);

		// Step CV_erode0:
		Mat cvErodeSrc = hslThresholdOutput;
		Mat cvErodeKernel = new Mat();
		Point cvErodeAnchor = new Point(-1, -1);
		double cvErodeIterations = 2.0;
		int cvErodeBordertype = Core.BORDER_CONSTANT;
		Scalar cvErodeBordervalue = new Scalar(-1);
		cvErode(cvErodeSrc, cvErodeKernel, cvErodeAnchor, cvErodeIterations, cvErodeBordertype, cvErodeBordervalue, cvErodeOutput);

		// Step Find_Contours0:
		Mat findContoursInput = cvErodeOutput;
		boolean findContoursExternalOnly = false;
		findContours(findContoursInput, findContoursExternalOnly, findContoursOutput);

		// Step Filter_Contours0:
		ArrayList<MatOfPoint> filterContoursContours = findContoursOutput;
		double filterContoursMinArea = 100.0;
		double filterContoursMinPerimeter = 0.0;
		double filterContoursMinWidth = 10.0;
		double filterContoursMaxWidth = 100.0;
		double filterContoursMinHeight = 40.0;
		double filterContoursMaxHeight = 1200.0;
		double[] filterContoursSolidity = {65.64748201438849, 100.0};
		double filterContoursMaxVertices = 1000000.0;
		double filterContoursMinVertices = 0.0;
		double filterContoursMinRatio = 0.0;
		double filterContoursMaxRatio = 1000.0;
    filterContours(filterContoursContours, filterContoursMinArea, filterContoursMinPerimeter, filterContoursMinWidth, filterContoursMaxWidth, filterContoursMinHeight, filterContoursMaxHeight, filterContoursSolidity, filterContoursMaxVertices, filterContoursMinVertices, filterContoursMinRatio, filterContoursMaxRatio, filterContoursOutput);

public static class UART {

  /**
   * This example program supports the following optional command arguments/options:
   *   "--device (device-path)"                   [DEFAULT: /dev/ttyAMA0]
   *   "--baud (baud-rate)"                       [DEFAULT: 38400]
   *   "--data-bits (5|6|7|8)"                    [DEFAULT: 8]
   *   "--parity (none|odd|even)"                 [DEFAULT: none]
   *   "--stop-bits (1|2)"                        [DEFAULT: 1]
   *   "--flow-control (none|hardware|software)"  [DEFAULT: none]
   *
   * @param args
   * @throws InterruptedException
   * @throws IOException
   */
  public static void Comm() throws InterruptedException, IOException {

      // !! ATTENTION !!
      // By default, the serial port is configured as a console port
      // for interacting with the Linux OS shell.  If you want to use
      // the serial port in a software program, you must disable the
      // OS from using this port.
      //
      // Please see this blog article for instructions on how to disable
      // the OS console for this port:
      // https://www.cube-controls.com/2015/11/02/disable-serial-port-terminal-output-on-raspbian/

      /*
      On the new Raspbian Jessie release as of May 2016 serial port is disabled by default , it has to be enabled in config.txt!
      To enable run next command to edit confix.txt:
      sudo nano /boot/config.txt
      Change enable_uart to 1 or add line if does not exist:
      enable_uart=1
      In the case of Rapsberry Pi 3 one more line has to be added to config.txt because serial ports are swapped!
      dtoverlay=pi3-miniuart-bt
      Reboot the Pi after update!
      */
      


      // create Pi4J console wrapper/helper
      // (This is a utility class to abstract some of the boilerplate code)
      final Console console = new Console();

      // print program title/header
      console.title("<-- The Pi4J Project -->", "Serial Communication Example");

      // allow for user to exit program using CTRL-C
      console.promptForExit();

      // create an instance of the serial communications class
      final Serial serial = SerialFactory.createInstance();

      // create and register the serial data listener
      serial.addListener(new SerialDataEventListener() {
          @Override
          public void dataReceived(SerialDataEvent event) {

              // NOTE! - It is extremely important to read the data received from the
              // serial port.  If it does not get read from the receive buffer, the
              // buffer will continue to grow and consume memory.

              // print out the data received to the console
              try {
                  console.println("[HEX DATA]   " + event.getHexByteString());
                  console.println("[ASCII DATA] " + event.getAsciiString());
              } catch (IOException e) {
                  e.printStackTrace();
              }
          }
      });

      try {
          // create serial config object
          SerialConfig config = new SerialConfig();

          // set default serial settings (device, baud rate, flow control, etc)
          //
          // by default, use the DEFAULT com port on the Raspberry Pi (exposed on GPIO header)
          // NOTE: this utility method will determine the default serial port for the
          //       detected platform and board/model.  For all Raspberry Pi models
          //       except the 3B, it will return "/dev/ttyAMA0".  For Raspberry Pi
          //       model 3B may return "/dev/ttyS0" or "/dev/ttyAMA0" depending on
          //       environment configuration.
         //config.device(SerialPort.getDefaultPort())
          //      .baud(Baud._38400)
            //    .dataBits(DataBits._8)
           //     .parity(Parity.NONE)
            //    .stopBits(StopBits._1)
            //    .flowControl(FlowControl.NONE);


                config = CommandArgumentParser.getSerialConfig(config);
          
          /*parse optional command argument options to override the default serial settings.
          if(args.length > 0){
              config = CommandArgumentParser.getSerialConfig(config, args);
          }
          */

          // display connection details
          console.box(" Connecting to: " + config.toString(),
                  " We are sending ASCII data on the serial port every 1 second.",
                  " Data received on serial port will be displayed below.");


          // open the default serial device/port with the configuration settings
          serial.open(config);

          // continuous loop to keep the program running until the user terminates the program
          while(console.isRunning()) {
              try {
                  // write a formatted string to the serial transmit buffer
                  serial.write("CURRENT TIME: " + new Date().toString());

                  // write a individual bytes to the serial transmit buffer
                  serial.write((byte) 13);
                  serial.write((byte) 10);

                  // write a simple string to the serial transmit buffer
                  serial.write("Second Line");

                  // write a individual characters to the serial transmit buffer
                  serial.write('\r');
                  serial.write('\n');

                  // write a string terminating with CR+LF to the serial transmit buffer
                  serial.writeln("Third Line");
              }
              catch(IllegalStateException ex){
                  ex.printStackTrace();
              }

              // wait 1 second before continuing
              Thread.sleep(1000);
          }

      }
      catch(IOException ex) {
          console.println(" ==>> SERIAL SETUP FAILED : " + ex.getMessage());
          return;
      }
  }//END of uartComm
}//END of UART