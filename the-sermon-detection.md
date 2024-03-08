# The sermon detection
We aim to develop a system capable of detecting sermon speeches within videos and accurately transcribing them into text. 
To achieve this, we can choose between one of the following options by selecting the most suitable LLM patfom.

## Processing with Clipping:

To optimize transcription processing and reduce costs, we can implement a feature allowing users to clip videos on our platform before transcription. By enabling users to specify the exact start and end times of the desired clip, we ensure that only the relevant audio segment is sent for processing by our Language and Linguistic Model (LLM). This targeted approach minimizes unnecessary processing of extraneous content and improves efficiency.

## Processing without Clipping:

### Option 1: Detection through speaker speaks (Azure)

To detect when a speaker speaks for a specific duration within a 60-minute video, we may follow these steps:

- Transcribe the Video:
Use a speech-to-text recognition service, such as Azure Cognitive Services Speech-to-Text, to transcribe the audio content of the entire 60-minute video into text.

- Segment the Transcription:
Break the transcription into smaller segments based on pauses, speaker changes, or other cues. This segmentation helps in identifying individual speaker turns.

- Speaker Turn Detection:
Analyze each segment to identify speaker turns. You can use techniques like speaker diarization to group consecutive speech segments by the same speaker.

- Calculate Speaker Durations:
Calculate the duration of each speaker turn. Keep track of the accumulated duration for each speaker.

- Detect Long Speaker Turns:
Identify speaker turns that exceed the desired duration (in this case, 10 minutes). If a speaker turn exceeds 10 minutes, mark it as a segment where the speaker speaks for the specified duration.

- Output Results:
Output the timestamps or segments where the speaker speaks for at least 10 minutes.

### Option 2: Pick a person which speaks the most in video/audio (Azure vs Google)
- Azure Speaker Recognition helps determine who is speaking in an audio clip. It verifies and identifies speakers based on their unique voice characteristics using voice biometry.
- To identify the person who speaks the most in a video or audio recording using Google Cloud Speech-to-Text, we can utilize a technique called speaker diarization



