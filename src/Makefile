#
# Makefile for firewalld-logging
#
BASE=firewalld-logging

PREFIX:=/usr/local
ETC=$(PREFIX)/etc
SYSCONFIG=$(ETC)/sysconfig
LIB:=$(PREFIX)/lib
SYSTEMD:=$(LIB)/systemd/system
LIBEXEC:=$(PREFIX)/libexec

MKDIR:=/usr/bin/mkdir -pv
INSTALL:=/usr/bin/install
LN:=/usr/bin/ln -vis

.PHONY: install

install:	$(BASE)-sysconfig $(BASE).service $(BASE) 
	$(MKDIR) $(SYSCONFIG) $(SYSTEMD) $(LIBEXEC)
	$(INSTALL) -m 644 -T $(BASE)-sysconfig $(SYSCONFIG)/$(BASE)
	$(INSTALL) -m 644 $(BASE).service $(SYSTEMD)/
	$(INSTALL) -m 750 $(BASE) $(LIBEXEC)/
	pushd $(LIBEXEC); $(LN) $(BASE) $(BASE)-start; $(LN) $(BASE) $(BASE)-stop
