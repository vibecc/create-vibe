SOURCES := $(shell find . -type f -name '*.cpp' ! -path './lib/examples/*' ! -path './docker/*')

TARGET := ./App
SOURCE_DIR := .

DIR_OBJ := .
COMPILER := g++

FLAGS = -std=c++17 -pthread -O3 $(DEV_EXTRA)
OBJ := $(SOURCES:.cpp=.o)
DEPS := $(SOURCES:.cpp=.d)

$(TARGET) : $(OBJ)
	$(COMPILER) $(OBJ) $(FLAGS) -o $(TARGET)

$(DIR_OBJ)/%.o : $(SOURCE_DIR)/%.cpp
	$(COMPILER) -c -MD $(FLAGS) $< -o $@

-include $(DIR_OBJ)/*.d

.PHONY: clean install all
clean:
	@rm -rf *.o $(TARGET) $(OBJ) $(DEPS)
	@rm -f $(TARGET)

install:
	sudo apt-get install -y g++ make

all:
	$(TARGET)
