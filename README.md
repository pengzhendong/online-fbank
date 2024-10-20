# online-fbank

Online-fbank is a wrapper of [kaldi-native-fbank](https://github.com/csukuangfj/kaldi-native-fbank). It can be used to extract streaming fbank or streaming LFR (Lower Frame Rate) fbank for FunASR-based automatic speech recognition models.

## Usage

- fbank

``` python
from online_fbank import OnlineFbank

fbank = OnlineFbank()
fbank.accept_waveform(audio_samples, is_last=True)
feats = fbank.get_frames()
```

- lower frame rate fbank

``` python
from online_fbank import OnlineFbank

fbank = OnlineFbank(window_type="hamming")
fbank.accept_waveform(audio_samples, is_last=True)
feats = fbank.get_lfr_frames(neg_mean=neg_mean, inv_stddev=inv_stddev)
```
