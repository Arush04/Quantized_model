# Quantized_model

Tasks achieved in the collab notebook:
1. Loading "google/gemma-2b-it" model and Quantizing it using llama.cpp.
  What is llama.cpp: llama.cpp is a powerful tool that facilitates the quantization of LLMs. It supports     various quantization methods, making it highly versatile for different use cases.   
2. Running the model on collab and evaluating performance metrics by calculating inference time and memory.  
3. Uploading our quantized model on huggingface to later run on mobile.

After Quantizing has been successful and model has been uploaded on Huggingface we use koboldcpp, which is an easy-to-use AI text-generation software for GGML and GGUF models. It's a single self contained distributable from Concedo, that builds off llama.cpp, and adds a versatile Kobold API endpoint.  
  
Steps to run the model on mobile  

1. Download [Termux](https://f-droid.org/repo/com.termux_118.apk) and install on mobile.
2. Open Termux and use the following commands.
3. `pkg update && pkg upgrade`
4. `pkg install python clang python-pip git openssl`
5. `pip install psutil`
6. `git clone https://github.com/LostRuins/koboldcpp && cd koboldcpp`
7. `make`
8. `pkg install wget`
9. `wget https://huggingface.co/sharmaarush/gemma-2b-it-GGUF-quantized/resolve/main/Q4_K_M.gguf`
10. `python koboldcpp.py --model Q4_K_M.gguf`
11. Switch to your browser (don't close Termux) and go to localhost:5001.

LLM performance on mobile can be checked in the koboldui itself as it provides inference time and memory, also allows you to play with other settings like temperature.
