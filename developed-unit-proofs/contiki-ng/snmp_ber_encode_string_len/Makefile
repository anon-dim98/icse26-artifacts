# Defines the root of the project.
# Be aware of how many directories deep you go!
ROOT = ../../../../../..

# Defines file(s) to link to harness, MUST be a full path!
# (We recommend $(ROOT)/os/... for defining these paths)
# Each file is space seperated, and multiple can be defined
LINK = $(ROOT)/os/net/app-layer/snmp/snmp-ber.c

# Harness to utilize, omit the extension!
H_ENTRY = esl

# Extra CBMC flags to be passed during CBMC analysis
H_CBMCFLAGS = --nondet-static --unwind 1 --unwindset snmp_ber_encode_string_len.0:20

# Extra header defintiions to be passed during compilation
H_DEF = 

# Extra CBMC includes to be passed during compilation
H_INC = -I../..

NET_DRIVER ?= NETSTACK_CONF_WITH_IPV6
MAC_DRIVER ?= MAC_CONF_WITH_NULLMAC
ROUTE_DRIVER ?= ROUTING_CONF_RPL_LITE

C_INC = \
	-I$(ROOT)/os \
	-I$(ROOT)/arch/cpu/native \
	-I$(ROOT)/arch/platform/native \
	-I$(ROOT)/cbmc/include \

# Include our special build file
MAKE_INCLUDE_PATH ?= ../../../..
include $(MAKE_INCLUDE_PATH)/Makefile.include
