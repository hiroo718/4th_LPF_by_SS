# 4th_LPF_by_SS
# 4th-order LPF via State-Space with Welch PSD estimation
# 状態空間法による4次ローパスフィルタ設計とWelch法によるパワースペクトル推定

## Overview / 概要
This program implements a 4th-order Low-Pass Filter (LPF) using State-Space representation,
consisting of two cascaded 2nd-order transfer functions.
The frequency response is estimated using Welch's Power Spectral Density (PSD) method.

本プログラムは、2次伝達関数を2段縦続接続した状態空間モデルにより
4次ローパスフィルタを実装し、Welch法によりパワースペクトル密度を推定します。

## Features / 特徴
- 4th-order LPF design via State-Space model / 状態空間モデルによる4次LPF設計
- Continuous-to-discrete conversion using Maclaurin series expansion of matrix exponential (func_c2d) / 行列指数関数のマクローリン展開による連続→離散変換（func_c2d）
- Step response simulation / ステップ応答シミュレーション
- Frequency response estimation via Welch PSD method / Welch法による周波数特性推定

## Parameters / パラメータ
| Parameter | Value |
|-----------|-------|
| Cutoff frequency / カットオフ周波数 | 20 Hz |
| Damping ratio / 減衰係数 (zeta) | 0.707 (Butterworth) |
| Sampling frequency / サンプリング周波数 | 40 kHz |

## Requirements / 必要環境
- Python 3.x
- numpy
- scipy
- matplotlib

## Usage / 使い方
```bash
python lpf_4th_order.py
```

## Output / 出力
- Figure 1: Step response in time domain / 時間領域のステップ応答
- Figure 2: Frequency response (Power spectrum ratio) in dB / 周波数特性（パワースペクトル比）[dB]

## Notes / 備考
func_c2d implements continuous-to-discrete conversion via Maclaurin series expansion
of the matrix exponential e^(AT), without relying on scipy built-in functions.

func_c2dは、scpiyの組み込み関数を使わず、
行列指数関数e^(AT)のマクローリン展開により連続→離散変換を実装しています。
