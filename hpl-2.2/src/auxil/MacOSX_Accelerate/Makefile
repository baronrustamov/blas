#  
#  -- High Performance Computing Linpack Benchmark (HPL)                
#     HPL - 2.2 - February 24, 2016                          
#     Antoine P. Petitet                                                
#     University of Tennessee, Knoxville                                
#     Innovative Computing Laboratory                                 
#     (C) Copyright 2000-2008 All Rights Reserved                       
#                                                                       
#  -- Copyright notice and Licensing terms:                             
#                                                                       
#  Redistribution  and  use in  source and binary forms, with or without
#  modification, are  permitted provided  that the following  conditions
#  are met:                                                             
#                                                                       
#  1. Redistributions  of  source  code  must retain the above copyright
#  notice, this list of conditions and the following disclaimer.        
#                                                                       
#  2. Redistributions in binary form must reproduce  the above copyright
#  notice, this list of conditions,  and the following disclaimer in the
#  documentation and/or other materials provided with the distribution. 
#                                                                       
#  3. All  advertising  materials  mentioning  features  or  use of this
#  software must display the following acknowledgement:                 
#  This  product  includes  software  developed  at  the  University  of
#  Tennessee, Knoxville, Innovative Computing Laboratory.             
#                                                                       
#  4. The name of the  University,  the name of the  Laboratory,  or the
#  names  of  its  contributors  may  not  be used to endorse or promote
#  products  derived   from   this  software  without  specific  written
#  permission.                                                          
#                                                                       
#  -- Disclaimer:                                                       
#                                                                       
#  THIS  SOFTWARE  IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
#  ``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES,  INCLUDING,  BUT NOT
#  LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
#  A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE UNIVERSITY
#  OR  CONTRIBUTORS  BE  LIABLE FOR ANY  DIRECT,  INDIRECT,  INCIDENTAL,
#  SPECIAL,  EXEMPLARY,  OR  CONSEQUENTIAL DAMAGES  (INCLUDING,  BUT NOT
#  LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
#  DATA OR PROFITS; OR BUSINESS INTERRUPTION)  HOWEVER CAUSED AND ON ANY
#  THEORY OF LIABILITY, WHETHER IN CONTRACT,  STRICT LIABILITY,  OR TORT
#  (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
#  OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE. 
# ######################################################################
#  
include Make.inc
#
# ######################################################################
#
INCdep           = \
   $(INCdir)/hpl_misc.h $(INCdir)/hpl_blas.h $(INCdir)/hpl_auxil.h
#
## Object files ########################################################
#
HPL_au0obj       = \
   HPL_dlacpy.o           HPL_dlatcpy.o          HPL_fprintf.o          \
   HPL_warn.o             HPL_abort.o            HPL_dlaprnt.o          \
   HPL_dlange.o
HPL_au1obj       = \
   HPL_dlamch.o
HPL_auxobj       = \
   $(HPL_au0obj) $(HPL_au1obj)
#
## Targets #############################################################
#
all     : lib
#
lib     : lib.grd
#
lib.grd : $(HPL_auxobj)
	$(ARCHIVER) $(ARFLAGS) $(HPLlib) $(HPL_auxobj)
	$(RANLIB) $(HPLlib)
	$(TOUCH) lib.grd
#
# ######################################################################
#
HPL_dlacpy.o           : ../HPL_dlacpy.c           $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_dlacpy.c
HPL_dlatcpy.o          : ../HPL_dlatcpy.c          $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_dlatcpy.c
HPL_fprintf.o          : ../HPL_fprintf.c          $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_fprintf.c
HPL_warn.o             : ../HPL_warn.c             $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_warn.c
HPL_abort.o            : ../HPL_abort.c            $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_abort.c
HPL_dlaprnt.o          : ../HPL_dlaprnt.c          $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_dlaprnt.c
HPL_dlange.o           : ../HPL_dlange.c           $(INCdep)
	$(CC) -o $@ -c $(CCFLAGS)  ../HPL_dlange.c
HPL_dlamch.o           : ../HPL_dlamch.c           $(INCdep)
	$(CC) -o $@ -c $(CCNOOPT)  ../HPL_dlamch.c
#
# ######################################################################
#
clean            :
	$(RM) *.o *.grd
#
# ######################################################################
