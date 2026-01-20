TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = SR06IOC01
# SR06IOC01.dbd will be created and installed
DBD += SR06IOC01.dbd

# SR06IOC01.dbd will be made up from these files:
SR06IOC01_DBD += base.dbd

# Include dbd files from all support applications:
SR06IOC01_DBD += asyn.dbd
SR06IOC01_DBD += drvAsynSerialPort.dbd
SR06IOC01_DBD += drvAsynIPPort.dbd
SR06IOC01_DBD += motorSupport.dbd
SR06IOC01_DBD += calcSupport.dbd
SR06IOC01_DBD += sscanSupport.dbd
SR06IOC01_DBD += asSupport.dbd
SR06IOC01_DBD += busySupport.dbd
SR06IOC01_DBD += GalilSupport.dbd

# Add all the support libraries needed by this IOC
SR06IOC01_LIBS += GalilSupport
SR06IOC01_LIBS += motor busy asyn calc sscan autosave

# SR06IOC01_registerRecordDeviceDriver.cpp derives from SR06IOC01.dbd
SR06IOC01_SRCS += SR06IOC01_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
SR06IOC01_SRCS_DEFAULT += SR06IOC01Main.cpp
SR06IOC01_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#SR06IOC01_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
SR06IOC01_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

