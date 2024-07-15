# Llama

An example of generating text with Llama 3 using MLX.
This example is created based on [mlx-examples](https://github.com/ml-explore/mlx-examples/tree/main/llms/llama)

### Setup

Install the dependencies:

```
pip install -r requirements.txt
```

Next, download and convert the model. 

Download the model in the `original` directory from [here](https://huggingface.co/meta-llama/Meta-Llama-3-8B-Instruct/tree/main/original).

Convert the weights with:

```
python convert.py --torch-path <path_to_torch_model>
```

To generate a 4-bit quantized model use the `-q` flag:

```
python convert.py --torch-path <path_to_torch_model> -q
```

By default, the conversion script will make the directory `mlx_model` and save
the converted `weights.npz`, `tokenizer.model`, and `config.json` there.


### Run

Once you've converted the weights to MLX format, you can interact with the
LlamA model:

```
python llama.py --prompt "hello"
```

Run `python llama.py --help` for more details.
