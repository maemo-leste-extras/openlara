SRCS=main.cpp \
     ../../libs/stb_vorbis/stb_vorbis.c \
     ../../libs/minimp3/minimp3.cpp \
     ../../libs/tinf/tinflate.c
CC=g++

SDL_CFLAGS := $(shell sdl2-config --cflags)
SDL_LDFLAGS := $(shell sdl2-config --libs)

CFLAGS=-DSDL2_GLES -D_GAPI_GLES2 -std=c++11 $(SDL_CFLAGS) -O3 -fno-exceptions -fno-rtti -ffunction-sections -fdata-sections -Wl,--gc-sections -DNDEBUG -D__SDL2__
LDFLAGS=-lGLESv2 -lEGL -lm -lrt -lpthread -lasound -ludev $(SDL_LDFLAGS)

INCLUDES+=-I../../

openlara :
	$(CC) $(CFLAGS) $(SRCS) $(INCLUDES) -o $@ $(LDFLAGS)

install : openlara
	install -d $(DESTDIR)$(PREFIX)/bin/
	install openlara $(DESTDIR)$(PREFIX)/bin/OpenLara

uninstall :
	rm -f $(DESTDIR)$(PREFIX)/bin/OpenLara

clean:
	rm -f OpenLara

