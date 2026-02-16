## Summary
This fork modifies the `gr-lora_sdr` Frame Sync block to:
1. Add a “multibin” SNR estimator that computes preamble signal energy by summing across \(2n\) FFT **edge** bins: \(n\) bins at the start and \(n\) bins at the end, rather than using only the expected peak FFT bin at DC.
2. Expose the complex FFT of the FIRST dechirped preamble symbol through an additional output port.

<p align="center">
  <img width="403" height="179" alt="image"
       src="https://github.com/user-attachments/assets/f4e49933-c9fc-4fe4-a6f2-b86108f5cd5e" />
</p>

### Modifications
- `multibin_bins`: Runtime control input that updates the number of edge bins used by the multibin SNR estimator  
  - e.g., PMT message "4" uses the first 4 plus last 4 bins when computing signal energy.
- `fft_preamble`: FFT of the first dechirped preamble symbol as it arrives (complex stream)
- **`log`: Extended output stream (float) - the multibin SNR computations (alongside the existing sync/SNR-related measurements) are accessible here**. See the block documentation for the output order.

## gr-lora_sdr
See: https://github.com/tapparelj/gr-lora_sdr

