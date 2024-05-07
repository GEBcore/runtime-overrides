# How to run your trace node

$ mkdir bevm-substitutes-tracing

$ cp 29_trace_bevm_runtime.compact.compressed.wasm  bevm-substitutes-tracing/

$ ./bevm-v0.1.6-trace --name=trace \
   --rpc-port 8087 --rpc-external --rpc-cors all \
   --chain=mainnet -d data --port 30333  \
   --pruning=archive --ethapi debug,trace,txpool \
   --trie-cache-size 1073741824 --db-cache 4096 \
   --runtime-cache-size 64 --wasm-runtime-overrides=./bevm-substitutes-tracing \
   --logs-request-timeout 30
