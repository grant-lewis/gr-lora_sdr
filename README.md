## Summary
This fork modifies the gr-lora_sdr Frame Sync block to (1) add a “multi-bin” SNR estimate that sums preamble signal energy across 2n FFT bins (n bins at the start and n bins at the end) instead of using only the peak bin, and (2) exposes the complex FFT of the first dechirped preamble symbol via an additional output port.

## gr-lora_sdr
See: https://github.com/tapparelj/gr-lora_sdr
