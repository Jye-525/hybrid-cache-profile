# hybrid-cache-profile

## Project Description

This project characterizes how key-value (KV) and recurrent state caches are created, updated, and consumed across layers during LLM inference. Starting from model architecture details, it examines selected Hugging Face implementations by tracing forward passes, pinpointing where cache/state is produced, and measuring memory usage per layer or layer group.

These measurements then drive a practical layer-aware optimization: instead of removing caching indiscriminately, the project identifies where full historical KV is truly required and where bounded, shared, compressed, or recurrent representations can preserve quality with lower memory cost.