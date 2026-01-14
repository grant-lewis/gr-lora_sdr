## Summary
This fork modifies gr-lora_sdr Frame sync block to (1) compute "multi-bin" SNR that sums signal energy over the strongest n FFT bins instead of only the peak bin, and (2) expose the complex FFT of the first dechirped preamble symbol on an additional output port.

## gr-lora_sdr
See: https://github.com/tapparelj/gr-lora_sdr