all: server client rdma_example

server:rdma_server.c
	gcc rdma_common.c rdma_server.c -libverbs -lrdmacm -o server
client: rdma_client.c
	gcc rdma_common.c rdma_client.c -libverbs -lrdmacm -o client
rdma_example: rdma_begin.c
	g++ -o rdma_example rdma_begin.c -libverbs 

.PHONY: clean

clean:
	rm -rf server client rdma_example