TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = Keithley6482Test
# Keithley6482Test.dbd will be created and installed
DBD += Keithley6482Test.dbd

# Keithley6482Test.dbd will be made up from these files:
Keithley6482Test_DBD += base.dbd

# Include dbd files from all support applications:
Keithley6482Test_DBD += stream.dbd
Keithley6482Test_DBD += asyn.dbd
Keithley6482Test_DBD += drvAsynIPPort.dbd

# Add all the support libraries needed by this IOC
Keithley6482Test_LIBS += stream
Keithley6482Test_LIBS += asyn

pcre_DIR += $(PCRE_LIB)

ifdef PCRE
Keithley6482Test_LIBS += pcre
endif


# Keithley6482Test_registerRecordDeviceDriver.cpp derives from Keithley6482Test.dbd
Keithley6482Test_SRCS += Keithley6482Test_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
Keithley6482Test_SRCS_DEFAULT += Keithley6482TestMain.cpp
Keithley6482Test_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#Keithley6482Test_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
Keithley6482Test_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

