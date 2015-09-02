# BOXLIB_HOME defines the directory in which we will find all the BoxLib code
# If you set BOXLIB_HOME as an environment variable, this line will be ignored
BOXLIB_HOME ?= /path/to/BoxLib/

NDEBUG    := t
MPI       := t
OMP       := 
PROF      :=
COMP      := gfortran
MKVERBOSE := t

include $(BOXLIB_HOME)/Tools/F_mk/GMakedefs.mak

include ./GPackage.mak
VPATH_LOCATIONS += .

include $(BOXLIB_HOME)/Src/F_BaseLib/GPackage.mak
VPATH_LOCATIONS += $(BOXLIB_HOME)/Src/F_BaseLib

include $(BOXLIB_HOME)/Src/LinearSolvers/F_MG/GPackage.mak
VPATH_LOCATIONS += $(BOXLIB_HOME)/Src/LinearSolvers/F_MG

amripple: $(objects) 
	$(LINK.f90) -o amripple $(objects) $(libraries)
	@echo SUCCESS

include $(BOXLIB_HOME)/Tools/F_mk/GMakerules.mak
