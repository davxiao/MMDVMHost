cmake_minimum_required (VERSION 3.0)
# Name our project
project (MMDVMHost)
# Create a variable that holds the path to our libwiringPi.so file
# set (WPI_PATH /home/alex/Development/wiringPi/wiringPi)
# Add the local ‘include’ directory and the wiringPi directory to grab headers
# include_directories (include ${WPI_PATH})
# Actually find the wiringPi library object
# find_library(WPI_LIB wiringPi HINTS ${WPI_PATH} NO_CMAKE_FIND_ROOT_PATH)
# Alert the user if we do not find it
#if(NOT WPI_LIB)
# message(FATAL_ERROR “wiringPi library not found”)
#endif()
# Add all the *.c files in our source directory to our executable output
FILE(GLOB SRC_FILES AMBEFEC.cpp BCH.cpp BPTC19696.cpp CASTInfo.cpp Conf.cpp CRC.cpp Display.cpp DMRControl.cpp DMRCSBK.cpp DMRData.cpp DMRDataHeader.cpp DMREMB.cpp DMREmbeddedData.cpp DMRFullLC.cpp DMRLookup.cpp DMRLC.cpp DMRNetwork.cpp DMRShortLC.cpp DMRSlot.cpp DMRSlotType.cpp DMRAccessControl.cpp DMRTA.cpp DMRTrellis.cpp DStarControl.cpp DStarHeader.cpp DStarNetwork.cpp DStarSlowData.cpp Golay2087.cpp Golay24128.cpp Hamming.cpp I2CController.cpp OLED.cpp LCDproc.cpp Log.cpp MMDVMHost.cpp MobileGPS.cpp Modem.cpp ModemSerialPort.cpp Mutex.cpp NetworkInfo.cpp Nextion.cpp NullDisplay.cpp NullModem.cpp NXDNAudio.cpp NXDNControl.cpp NXDNConvolution.cpp NXDNCRC.cpp NXDNFACCH1.cpp NXDNLayer3.cpp NXDNLICH.cpp NXDNLookup.cpp NXDNNetwork.cpp NXDNSACCH.cpp NXDNUDCH.cpp P25Audio.cpp P25Control.cpp P25Data.cpp P25LowSpeedData.cpp P25Network.cpp P25NID.cpp P25Trellis.cpp P25Utils.cpp POCSAGControl.cpp POCSAGNetwork.cpp QR1676.cpp RemoteControl.cpp RS129.cpp RS241213.cpp RSSIInterpolator.cpp SerialController.cpp SerialPort.cpp SHA256.cpp StopWatch.cpp Sync.cpp TFTSerial.cpp TFTSurenoo.cpp Thread.cpp Timer.cpp UDPSocket.cpp UMP.cpp UserDB.cpp UserDBentry.cpp Utils.cpp YSFControl.cpp YSFConvolution.cpp YSFFICH.cpp YSFNetwork.cpp YSFPayload.cpp)
add_executable(MMDVMHost ${SRC_FILES})
# Link the pre-compiled wiringPi library to the executable we just declared
target_link_libraries(MMDVMHost ArduiPi_OLED wiringPi pthread)

