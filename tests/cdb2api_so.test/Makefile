include $(TESTSROOTDIR)/testcase.mk
export TEST_TIMEOUT=1m

CFLAGS+=-Wall -I$(SRCHOME)/cdb2api -I$(SRCHOME)/bbinc
CDB2LIBS=$(SYSPATH) -L$(SRCHOME)/cdb2api -lcdb2api -ldl -L$(SRCHOME)/protobuf/ -lcdb2protobuf -lprotobuf-c -lpthread -lssl -lcrypto -L$(SRCHOME)/bb -lbb

tool: cdb2_client

cdb2_client: cdb2_client.o
	$(CC) -o $@ $< $(CDB2LIBS)

%.o: %.c
	$(CC) -o $@ -g -c $< $(CFLAGS)

