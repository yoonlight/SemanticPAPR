# Simulation

- 2023-11-09

```sh
python main.py --snr 0 --numepoch 100 --precoding 0 --mapping 0 --lamb 0 --thres 0 --clip 0 --fading 0 --BatchSize 864 --lr 1e-4
```

- 2023-11-10

- simulation Channel standard deviation (sigma) 계산 방식 변경

```sh
python main.py --snr 10 --numepoch 100 --precoding 0 --mapping 0 --lamb 0 --thres 0 --clip 0 --fading 0 --BatchSize 864 --lr 1e-4
```

- 변경 전/후

```sh
nohup python main.py --snr 10 --numepoch 100 --precoding 0 --mapping 0 --lamb 0 --thres 0 --clip 0 --fading 0 --BatchSize 864 --lr 1e-3 >> 2023111
0_channel_1.out 2>&1 &
nohup python main.py --snr 10 --numepoch 100 --precoding 0 --mapping 0 --lamb 0 --thres 0 --clip 0 --fading 0 --BatchSize 864 --lr 1e-3 >> 20231110_channel_2.out 2>&1 &
```

- 2023-11-12
- torch metrics PSNR 사용

```sh
nohup python main.py --snr 10 --numepoch 100 --precoding 0 --mapping 0 --lamb 0 --thres 0 --clip 0 --fading 0 --BatchSize 864 --lr 1e-3 >> logs/20231112_torch_metrics.out 2>&1 &
```

- 실험 결과 분석 자체 PSNR과 torch metrics PSNR 값의 차이가 조금씩 남
- torchmetrics의 값이 살짝 더 낮음

- Error
- ImportError: cannot import name 'ParamSpec' from 'typing_extensions' (/opt/conda/lib/python3.8/site-packages/typing_extensions.py)
  - [solution](https://stackoverflow.com/questions/72980064/from-typing-extensions-import-paramspec-importerror-cannot-import-name-paramsp)
- /opt/conda/lib/python3.8/site-packages/requests/__init__.py:89: RequestsDependencyWarning: urllib3 (2.0.7) or chardet (3.0.4) doesn't match a supported version!
  warnings.warn("urllib3 ({}) or chardet ({}) doesn't match a supported "

```sh
pip uninstall typing_extensions
```
