# ViLingo

**ViLingo** is a pipeline with webservice for automated translating videos from Russian language into **12** foreign languages.


The following ML models were used:
* **Demucs** - for separating voices from other sounds (dualization task)
* **WhisperX** - for performing STT and getting timestamps for each phrase
* **NLLB-200** - for translation of the text
* **Wav2Lip** - syncing lips of speaker with the voice 
* **Coqui xtts_v2** - for TTS and voice cloning of the speaker

Note, that each phrase is processed separately, which helps to make pronounce each phrase with the voice of 
the corresponding speaker.

# Examples

Please find some examples of our work
[there](https://drive.google.com/drive/folders/1LqOT3hCsz6AI9shP1lP4ya5DxC1VzaW-?usp=drive_link).

# Running

Run the following command from `model` directory:
```bash
python3.10 main.py [path_to_video] [language]
```

Language can be `en` or `fr`, for example.

## System

The code was tested on Ubuntu 22.04.01 .

## Python 3.10

```bash
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.10
```

## Libraries

```bash
python3.10 -m pip install git+https://github.com/m-bain/whisperx.git
python3.10 -m pip install transformers==4.33.0
python3.10 -m pip install demucs==4.0.1
python3.10 -m pip install TTS==0.20.3
python3.10 -m pip install pydub==0.25.1
sudo apt install ffmpeg
```

# Hardware requirements

The code was tested on with Tesla-V100 1x32GB on remote server.
