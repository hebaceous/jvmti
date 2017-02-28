ifeq ($(shell uname), Linux)
  CC         = g++ 
  LIBLINK    = -shared 
  INCLUDEDIR = -I$(JAVA_HOME)/include -I$(JAVA_HOME)/include/linux
  TARGET     = libencrypt.so
endif

ifeq ($(shell uname), Darwin)
  CC		 = g++ 
  LIBLINK    = -dynamiclib
  TARGET     = libencrypt.dylib
  INCLUDEDIR = -I/System/Library/Frameworks/JavaVM.framework/Headers
endif

OBJS = encrypt.o

$(TARGET):$(OBJS)
	$(CC) $(LIBLINK) -o $(TARGET) $(OBJS)

encrypt.o: encrypt.cpp
	$(CC) $(INCLUDEDIR) -c encrypt.cpp -fPIC

.PHONY:clean
clean:
	rm $(TARGET) $(OBJS)