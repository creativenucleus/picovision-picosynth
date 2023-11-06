# PicoSynth library ad-hoc reference

Audio functionality is supported by the [PicoSynth library](https://github.com/pimoroni/pimoroni-pico/tree/main/libraries/pico_synth) which allows you to create multiple voice channels with ADSR (attack decay sustain release) envelopes. It provides a similar set of functionality to the classic SID chip in the Commodore 64.

## picosynth.PicoSynth

### constructor

### set_volume()

### get_volume()

### adjust_volume()

### play_sample()

#### argument: data (required)

Play the provided 16-bit audio sample. data must point to a bytearray that contains 16-bit PCM data. The number of samples is retrieved from the array's length.

### play()

### stop()

### channel()

Returns a picosynth.Channel object, which can then be configured with voice, ADSR envelope, etc.

## picosynth.Channel

### configure()

[ADSR explained here](https://github.com/pimoroni/pimoroni-pico/blob/b4451c3bdc06235a1358a5a8aabd008647ed9f8a/libraries/pico_synth/pico_synth.hpp#L18C1-L21C103)

- Attack:  number of milliseconds it takes for a note to hit full volume
- Decay:   number of milliseconds it takes for a note to settle to sustain volume
- Sustain: percentage of full volume that the note sustains at (duration implied by other factors)
- Release: number of milliseconds it takes for a note to reduce to zero volume after it has ended

#### argument: waveforms (default: None)

This is a bitmap, with the following available values:

- WAVE
- SINE
- TRIANGLE
- SAW
- SQUARE
- NOISE

These can be combined, e.g. Channel.SINE | Channel.TRIANGLE

#### argument: frequency (default: None)

#### argument: volume (default: None)

0.0 to 1.0

#### argument: attack (default: None)

0.0s to 65.5 (seconds)

#### argument: decay (default: None)

0.0s to 65.5 (seconds)

#### argument: sustain (default: None)

0.0 to 1.0

#### argument: release (default: None)

0.0s to 65.5 (seconds)

#### argument: pulse_width (default: None)

0.0 to 1.0

### restore()

### waveforms()

### waveforms(waveforms)

### frequency()

### frequency(frequency)

Frequency in Hz (0 to 65535). A4 is 440Hz.

### volume()

### volume(volume)

### attack_duration()

### attack_duration(duration)

### decay_duration()

### decay_duration(duration)

### sustain_level()

### sustain_level(level)

### release_duration()

### release_duration(duration)

### pulse_width()

### pulse_width(width)

### trigger_attack()

Start the channel playing

### trigger_release()

Stop the channel playing

### play_tone(...)

#### argument: frequency (required)

#### argument: volume (default: None)

#### argument: attack (default: None)

#### argument: release (default: None)

## Examples

### Minimal

This will be a tone. Mind your ears if you're wearing headphones!
```
from picosynth import PicoSynth, Channel

synth = PicoSynth()
synth.play()

channel = synth.channel(0)
channel.configure(waveforms=Channel.SINE)
channel.frequency(440)
channel.trigger_attack()
```

## References

- https://github.com/pimoroni/picovision/blob/main/modules/picosynth/picosynth.c
- https://github.com/pimoroni/picovision/blob/main/modules/picosynth/picosynth.cpp
- https://github.com/pimoroni/pimoroni-pico/blob/main/micropython/modules/cosmic_unicorn/README.md#audio
- https://github.com/pimoroni/pimoroni-pico/blob/b4451c3bdc06235a1358a5a8aabd008647ed9f8a/micropython/examples/stellar_unicorn/numpy/eighties_super_computer.py#L93-L94
