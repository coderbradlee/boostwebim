all:websocket

CXXFLAGS ?= -std=c++11 -g -O3 -L. -L/usr/local/lib -L. -lcrypto -lboost_program_options -lboost_filesystem -lboost_coroutine -lboost_system -lboost_thread -lpthread -lboost_context -lboost_date_time -lboost_log_setup -lboost_log
daemon:websocketDaemon

websocketDaemon: websocket.cpp base64.cpp modp_base64/modp_b64.cc renesolalog.cpp
	g++ $(CXXFLAGS) -DDAEMON modp_base64/modp_b64.cc renesolalog.cpp base64.cpp websocket.cpp -o websocketDaemon
	rm -f *.o

websocket: dataframe.cpp dataframe_parser.cpp main.cpp reply.cpp request_handler.cpp request_parser.cpp room.cpp server.cpp session.cpp
	g++ $(CXXFLAGS) dataframe.cpp dataframe_parser.cpp main.cpp reply.cpp request_handler.cpp request_parser.cpp room.cpp server.cpp session.cpp -o websocket
	rm -f *.o

clean:
	rm -f *.o
cleanall:
	rm -f *.o websocket websocketDaemon
