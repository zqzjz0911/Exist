#makefile�ļ�����ָ��
#���make�ļ�����makefile��ֱ��ʹ��make�Ϳ��Ա���
#���make�ļ�������makefile������test.txt����ôʹ��make -f test.txt

#------------------------------------------������ϵͳ32λ64λ--------------------------------------------------------
#SYS_BIT=$(shell getconf LONG_BIT)
#SYS_BIT=$(shell getconf WORD_BIT)
SYS_BIT=$(shell getconf LONG_BIT)
ifeq ($(SYS_BIT),32)
	CPU =  -march=i686 
else 
	CPU = 
endif

#------------------------------------------�༭��--------------------------------------------------------

#c++���빤��
CC = g++ 
#apacheģ����밲װ����
APXS = apxs 

#------------------------------------------�༭��End--------------------------------------------------------

#------------------------------------------Ŀ¼--------------------------------------------------------

#����Ŀ��/�ļ�����Ŀ¼
VPATH = $(OBJ_OUTPUT_DIR) $(H_DIR) $(H_CPP)
MDK_HOME = ../Micro-Development-Kit
BSTRUCT_HOME = ../bstruct
PROTOCOL = ../protocl

#���Ŀ¼
OBJ_OUTPUT_DIR=./output
OUTPUT_DIR=./bin
$(shell mkdir $(OBJ_OUTPUT_DIR))
$(shell mkdir $(OUTPUT_DIR))

#.cppĿ¼
CPP_DIR= $(PROTOCOL)

#.hĿ¼
H_DIR= $(PROTOCOL)

#------------------------------------------Ŀ¼End--------------------------------------------------------

#------------------------------------------����ѡ��--------------------------------------------------------

#SO�ļ�����ѡ��
CFLAGS= -O -g -fPIC -Wall -D_REENTRANT -DUSE_APACHE -DNO_STRING_CIPHER $(CPU) 

#���漶��
WARNING_LEVEL += -O3 

#ͷ�ļ�Ŀ¼��-I Ŀ¼
INCLUDE = -I. -I../include -I$(MDK_HOME)/include -I$(BSTRUCT_HOME)/include 

#��Ŀ¼�����ļ�:-L Ŀ¼ -����
#SYSLIB = -lnsl -lc -lm -lpthread -lstdc++ 
LIB = -lnsl -lc -lm -lpthread -lstdc++ 

#��̬�⣺.a�ļ�·����
LIB += $(MDK_HOME)/lib/mdk.a $(BSTRUCT_HOME)/lib/bstruct.a 


#------------------------------------------����ѡ��End--------------------------------------------------------

#��Ŀ������ļ�
MAIN =



#------------------------------------------���--------------------------------------------------------
#��������ĳ����ļ���
OUTPUT = Guide

#Ŀ���ļ�
OBJ_PRO = $(notdir $(patsubst %.cpp,%.o,$(wildcard *.cpp))) 
OBJ_PROTOCOL = $(notdir $(patsubst %.cpp,%.o,$(wildcard $(PROTOCOL)/*.cpp))) 


#������Ŀ���ļ�
DEPENDENCE = $(OBJ_PRO) $(OBJ_PROTOCOL) 

#������Ŀ����Ҫ����������Դ�ļ���Ŀ���ļ�(��Ŀ¼)
OBJ = $(addprefix $(OBJ_OUTPUT_DIR)/, $(OBJ_PRO)) $(addprefix $(OBJ_OUTPUT_DIR)/, $(OBJ_PROTOCOL)) 

#------------------------------------------���End--------------------------------------------------------

#-------------------------------------------����ָ��-----------------------------------------------------
#����EXE
#������
#$(OUTPUT_DIR)/$(OUTPUT): $(MAIN)$(DEPENDENCE)										������ϵ
#	@echo "Complie (OUTPUT_DIR)/$(OUTPUT)"
#	$(CC) -o $@ $(CFLAGS)$(WARNING_LEVEL)$(INCLUDE)$(MAIN)$(OBJ)$(LIB)		gcc����ָ��
#	@echo ""
#	@echo "$(OUTPUT_DIR)/$(OUTPUT) complie finished"
#	@echo ""
#	@echo ""
#	@echo ""
#	@echo ""

$(OUTPUT_DIR)/$(OUTPUT):$(MAIN)$(DEPENDENCE)
	@echo "Complie (OUTPUT_DIR)/$(OUTPUT)"
	@echo ""
	$(CC) -o $@ $(CFLAGS)$(WARNING_LEVEL)$(INCLUDE)$(MAIN)$(OBJ)$(LIB)
	@echo ""
	@echo "$(OUTPUT_DIR)/$(OUTPUT) complie finished"
	@echo ""
	@echo ""
	@echo ""
	@echo ""

#-----------------------------------------��������.A��̬��---------------------------------------------------
#$(OUTPUT_DIR)/$(OUTPUT):$(MAIN)$(DEPENDENCE)
#	@echo "Complie $(OUTPUT_DIR)/$(OUTPUT)"
#	@echo ""
#	ar -r $@ $(OBJ)
#	@echo ""
#	@echo "$(OUTPUT_DIR)/$(OUTPUT) complie finished"
#	@echo ""
#	@echo ""
#	@echo ""
#	@echo ""

#-----------------------------------------��������SO��̬��---------------------------------------------------
#������
#$(OUTPUT_DIR)/$(OUTPUT): $(DEPENDENCE)											������ϵ
#	@echo "Complie $(OUTPUT_DIR)/$(OUTPUT)"
#	$(CC) -o $@ -shared $(CFLAGS)$(WARNING_LEVEL)$(INCLUDE)$(OBJ)$(LIB)		gcc����ָ��
#	@echo ""
#	@echo "$(OUTPUT_DIR)/$(OUTPUT) complie finished"
#	@echo ""
#	@echo ""
#	@echo ""
#	@echo ""


#------------------------------------------����Object----------------------------------------------------
#����������object����
#$(OBJ_OUTPUT_DIR)/GameSerFrm.o: main/GameSerFrm.cpp main/GameSerFrm.h main/GameSerCPU.h com/ComDef.h com/XXSocket.h tool/DBTool.h	������ϵ
#	@echo "Complie GameSerFrm.o"
#	$(CC) -c -o $*.o $(CFLAGS)$(WARNING_LEVEL)$(INCLUDE)main/GameSerFrm.cpp											gcc����ָ��
#	@echo ""
#	@echo "$(OBJ_OUTPUT_DIR)/GameSerFrm.o complie finished"
#	@echo ""
#	@echo ""

#����������object����
#$(OBJ_PRO):%.o:%.cpp %.h
#	@echo "Complie $(OBJ_OUTPUT_DIR)/$*.o"
#	@echo ""
#	$(CC) -c -o $(OBJ_OUTPUT_DIR)/$*.o $(CFLAGS)$(WARNING_LEVEL)$(INCLUDE) $*.cpp
#	@echo ""
#	@echo "$(OBJ_OUTPUT_DIR)/$*.o complie finished"
#	@echo ""
#	@echo ""
#	@echo ""
#	@echo ""


$(OBJ_PRO):%.o:%.cpp %.h
	@echo "Complie $(OBJ_OUTPUT_DIR)/$*.o"
	@echo ""
	$(CC) -c -o $(OBJ_OUTPUT_DIR)/$*.o $(CFLAGS)$(WARNING_LEVEL)$(INCLUDE) $*.cpp
	@echo ""
	@echo "$(OBJ_OUTPUT_DIR)/$*.o complie finished"
	@echo ""
	@echo ""
	@echo ""
	@echo ""

$(OBJ_PROTOCOL):%.o:%.cpp %.h
	@echo "Complie $(OBJ_OUTPUT_DIR)/$*.o"
	@echo ""
	$(CC) -c -o $(OBJ_OUTPUT_DIR)/$*.o $(CFLAGS)$(WARNING_LEVEL)$(INCLUDE) $(PROTOCOL)/$*.cpp
	@echo ""
	@echo "$(OBJ_OUTPUT_DIR)/$*.o complie finished"
	@echo ""
	@echo ""
	@echo ""
	@echo ""




install:
#------------------------------------------��װ----------------------------------------------------
#------------------------------------------��װapacheģ��----------------------------------------------------
#������apxs -a -i -n ģ���� so�ļ���
#apxs -a -i -n test $(OBJ_OUTPUT_DIR)/$(OUTPUT)
	apxs -a -i -n pfadurl $(OBJ_OUTPUT_DIR)/$(OUTPUT)





#------------------------------------------�������±���----------------------------------------------------
clean:
	-rm -f $(OUTPUT_DIR)/$(OUTPUT) $(OBJ_OUTPUT_DIR)/*.o
	
.PHONY: clean


#------------------------------------------apache����----------------------------------------------------

start:
	$(APACHE_BIN)/apachectl start

stop:
	$(APACHE_BIN)/apachectl stop

ps:
	ps -ae|grep http