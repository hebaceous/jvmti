ifeq ($(shell uname), Linux)
  CC         = g++ 
  LIBLINK    = -shared 
  INCLUDEDIR = -I$(JAVA_HOME)/include -I$(JAVA_HOME)/include/linux
  TARGET     = libdecrypt.so
endif

ifeq ($(shell uname), Darwin)
  CC		 = g++ 
  LIBLINK    = -dynamiclib
  TARGET     = libdecrypt.dylib
  INCLUDEDIR = -I/System/Library/Frameworks/JavaVM.framework/Headers
endif

OBJS = decrypt.o

$(TARGET):$(OBJS)
	$(CC) $(LIBLINK) -o $(TARGET) $(OBJS)

decrypt.o: decrypt.cpp
	$(CC) $(INCLUDEDIR) -c decrypt.cpp -fPIC

.PHONY:clean
clean:
	rm $(TARGET) $(OBJS)