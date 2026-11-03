# IGEM-JamboreeQA

Pipeline that extracts English speech (transcripts) from audio/video, using
[sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) with Silero VAD and Whisper `small.en`.

```
media --ffmpeg--> 16 kHz mono wav --Silero VAD--> speech segments --Whisper small.en--> .txt / .srt / .json
```

## Usage
```bash
pip install -r requirements.txt   # needs ffmpeg on PATH
scripts/download_models.sh        # ~1 GB into ./models (git-ignored)
python -m src.jamboree_qa.pipeline path/to/video.mp4 -o output
```
Outputs: `<name>.txt` (plain), `<name>.srt` (timestamped), `<name>.json` (segments).
