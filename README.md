# picovision-picosynth

from picosynth import PicoSynth, Channel

## picosynth.PicoSynth

### Constructor

synth = PicoSynth()

## picosynth.Channel

### restore()

### waveforms()
### waveforms(waveforms)
### frequency()
### frequency(frequency)
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

start the channel playing
### trigger_release() # stop the channel playing
### play_tone(frequency, volume=None, attack=None, release=None)

### configure()

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

#### argument: attack (default: None)

#### argument: decay (default: None)

#### argument: sustain (default: None)

#### argument: release (default: None)

#### argument: pulse_width (default: None)


 { MP_ROM_QSTR(MP_QSTR___del__), MP_ROM_PTR(&Channel___del___obj) },
    { MP_ROM_QSTR(MP_QSTR_configure), MP_ROM_PTR(&Channel_configure_obj) },
    { MP_ROM_QSTR(MP_QSTR_restore), MP_ROM_PTR(&Channel_restore_obj) },
    { MP_ROM_QSTR(MP_QSTR_waveforms), MP_ROM_PTR(&Channel_waveforms_obj) },
    { MP_ROM_QSTR(MP_QSTR_frequency), MP_ROM_PTR(&Channel_frequency_obj) },
    { MP_ROM_QSTR(MP_QSTR_volume), MP_ROM_PTR(&Channel_volume_obj) },
    { MP_ROM_QSTR(MP_QSTR_attack_duration), MP_ROM_PTR(&Channel_attack_duration_obj) },
    { MP_ROM_QSTR(MP_QSTR_decay_duration), MP_ROM_PTR(&Channel_decay_duration_obj) },
    { MP_ROM_QSTR(MP_QSTR_sustain_level), MP_ROM_PTR(&Channel_sustain_level_obj) },
    { MP_ROM_QSTR(MP_QSTR_release_duration), MP_ROM_PTR(&Channel_release_duration_obj) },
    { MP_ROM_QSTR(MP_QSTR_pulse_width), MP_ROM_PTR(&Channel_pulse_width_obj) },
    { MP_ROM_QSTR(MP_QSTR_trigger_attack), MP_ROM_PTR(&Channel_trigger_attack_obj) },
    { MP_ROM_QSTR(MP_QSTR_trigger_release), MP_ROM_PTR(&Channel_trigger_release_obj) },
    { MP_ROM_QSTR(MP_QSTR_play_tone), MP_ROM_PTR(&Channel_play_tone_obj) },


self.channel = synth.channel(chIndex)

        # waveforms you can use are NOISE, SQUARE, SAW, TRIANGLE, SINE, or WAVE
        # you can combine more than one, like this: waveforms=Channel.SQUARE | Channel.SAW,
        self.channel.configure(**conf)


    { MP_ROM_QSTR(MP_QSTR_NOISE), MP_ROM_INT(128) },
    { MP_ROM_QSTR(MP_QSTR_SQUARE), MP_ROM_INT(64) },
    { MP_ROM_QSTR(MP_QSTR_SAW), MP_ROM_INT(32) },
    { MP_ROM_QSTR(MP_QSTR_TRIANGLE), MP_ROM_INT(16) },
    { MP_ROM_QSTR(MP_QSTR_SINE), MP_ROM_INT(8) },
    { MP_ROM_QSTR(MP_QSTR_WAVE), MP_ROM_INT(1) },
};

STATIC const mp_rom_map_elem_t PicoSynth_locals_dict_table[] = {
    { MP_ROM_QSTR(MP_QSTR___del__), MP_ROM_PTR(&PicoSynth___del___obj) },
    { MP_ROM_QSTR(MP_QSTR_set_volume), MP_ROM_PTR(&PicoSynth_set_volume_obj) },
    { MP_ROM_QSTR(MP_QSTR_get_volume), MP_ROM_PTR(&PicoSynth_get_volume_obj) },
    { MP_ROM_QSTR(MP_QSTR_adjust_volume), MP_ROM_PTR(&PicoSynth_adjust_volume_obj) },
    { MP_ROM_QSTR(MP_QSTR_play_sample), MP_ROM_PTR(&PicoSynth_play_sample_obj) },
    { MP_ROM_QSTR(MP_QSTR_play), MP_ROM_PTR(&PicoSynth_play_synth_obj) },
    { MP_ROM_QSTR(MP_QSTR_stop), MP_ROM_PTR(&PicoSynth_stop_playing_obj) },
    { MP_ROM_QSTR(MP_QSTR_channel), MP_ROM_PTR(&PicoSynth_synth_channel_obj) },
