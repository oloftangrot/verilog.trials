#===================================================================
#
# Makefile
# --------
# Makefile for building sip_master simulations.
#
#
# Author: Olof Tångrot
# Copyright (c) 2015, Olof Tångrot
# All rights reserved.
# 
# Redistribution and use in source and binary forms, with or 
# without modification, are permitted provided that the following 
# conditions are met: 
# 
# 1. Redistributions of source code must retain the above copyright 
#    notice, this list of conditions and the following disclaimer. 
# 
# 2. Redistributions in binary form must reproduce the above copyright 
#    notice, this list of conditions and the following disclaimer in 
#    the documentation and/or other materials provided with the 
#    distribution. 
# 
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS 
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT 
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS 
# FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE 
# COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, 
# INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, 
# BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
# LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER 
# CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, 
# STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
# ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF 
# ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
#
#===================================================================

SPI_MAS_SRC = SPI_master.v
SPI_TB_SRC = TB_SPI_MAS.v

CC=iverilog


all: spi_master.sim 10bit_spi_master.sim

10bit_spi_master.sim: SPI_10bit_master.v TB_SPI_10bit_MAS.v
	$(CC) -o $@ $^

spi_master.sim:  $(SPI_TB_SRC) $(SPI_MAS_SRC)
	$(CC) -o $@ $^

sim-master: spi_master.sim
	./spi_master.sim


clean:
	rm -f *.sim
	rm *.vcd
	rm *~


help:
	@echo "Supported targets:"
	@echo "------------------"
	@echo "all:            Build all simulation targets."
	@echo "spi_master:     Build the uart simulation target."
	@echo "sim-master:     Run the SPI master simulation."
	@echo "clean:          Delete all built files."

#===================================================================
# EOF Makefile
#===================================================================

