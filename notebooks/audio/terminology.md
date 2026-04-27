Sample rate - The number of samples of audio carried per second. Parameter of microphone, that allows to capture certain amount of count samples. (Similar as refresh rate of camera)

Human can hear up to 20 kHz (20000 Hz) frequency, so the sample rate must be at least 40 kHz to capture all frequencies. Common sample in mirchophones is 44.1 kHz, which allows to capture frequencies up to 22.05 kHz.

Neural networks tipically use sample rates of 16 kHz. If we have larger sample rate, we need to downsample the audio. Fortunaltly we loose some of the information. (In computer vision it would be like reducing the resoltuion of the image)

Aliasing - when we downsample to a sample rate too low, we can end up with to low frequency, that unable to capture all the original information and lead us to distorted audio.

Fourier transform - mathematical operation that transforms a signal from time domain to frequency domain. It allows us to analyze the frequency content of the audio signal.

With spectograms we can see how the frequency content is chaning over time. In spectograme we usauly show only magnitude of the frequencies. We can also show phase, it visualy it's not very useful, because looks more like a noise.

All neural network usualy use only magnitue.

If we want invert the spectogtam back to audio, we still need the phase information.
To do that we can use Griffin-Lim algorithm, which is an iterative method to estimate the phase from the magnitude spectrogram. 

But in Neural Networks like wav2vec, we usually pass raw audio

In models like whisper, we use spectograms as input.

https://www.youtube.com/watch?v=55QWsm1itKo