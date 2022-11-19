# Parameter-Efficient Fine-Tuning Design Spaces

This repository contains the PyTorch implementation of the work *Parameter-Efficient Fine-Tuning Design Spaces* (under review at ICLR 2023).


## Usage

One needs to setup the enrironment before running the experiments.

### Setup

```
cd models
pip install -e .
```

### Experiments

Evaluating the S4-model (`PEFT` is the alias) with the RoBERTa backbone on GLUE

```
export TASK_NAME=sst-2

python run_glue.py \
  --model_name_or_path roberta-base-uncased \
  --task_name $TASK_NAME \
  --do_train \
  --do_eval \
  --max_seq_length 128 \
  --per_device_train_batch_size 16 \
  --learning_rate 5e-5 \
  --num_train_epochs 10.0 \
  --output_dir /tmp/$TASK_NAME \
  --overwrite_output_dir \
  --train_adapter \
  --adapter_config PEFT
```

## TODO

* Polish code and documentation
* Add more experiments


## License

This project is licensed under the Apache-2.0 License.
