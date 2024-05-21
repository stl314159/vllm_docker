# VLLM OpenAI Docker Container

This Docker container is designed to run the VLLM OpenAI model. It is configured to run on NVIDIA GPUs and uses the Hugging Face library for model management.

## Features

- The container uses the latest VLLM OpenAI image.
- It is configured to use NVIDIA GPUs, with specific GPU indices defined in the [``docker-compose.yml``] file.
- The container uses the Hugging Face library for model management, with the cache directory mapped to `~/.cache/huggingface` on the host machine.
- The Hugging Face Hub token is passed as an environment variable.
- The model to be run is passed as a command-line argument to the container.

## How to Run

1. Ensure Docker and Docker Compose are installed on your machine.
2. Clone the repository and navigate to the directory containing the [``docker-compose.yml``] file.
3. Copy the [``.env.example``] file to a new file named [``.env``] in the same directory.
4. Edit the [``.env``] file to include your Hugging Face Hub token and the model you wish to run.
5. Run the following command in your terminal:

```sh
docker-compose up
```

This will start two services, `vllm_gpu_0` and `vllm_gpu_1`, each running on a different GPU and exposing different ports (8000 and 8001 respectively).

Please note that the GPUs and ports are configured in the [`docker-compose.yml`] file and can be adjusted as needed.