# DX7 to OP-XY / Tonverk Multisample Patch Maker

Convert DX7 SYSEX patches to multisamples for **OP-XY** or **Elektron Tonverk**.

Forked from [spacejam/tv7-js](https://github.com/spacejam/tv7-js) with added OP-XY support and retro 80s DX7 aesthetic.

## Features

- 🎹 Load DX7 SYSEX bank files (.syx)
- 🎵 Generate multisamples across any MIDI note range
- 🎛️ Preview patches with on-screen keyboard
- 📦 Export to two formats:
  - **OP-XY** (.preset with individual WAVs + patch.json) - Default
  - **Elektron Tonverk** (.elmulti + concatenated WAV)
- 🔊 Includes 50+ example DX7 patch banks
- 🎨 Classic 80s DX7 interface with teal LCD-style display

## Quick Start

### Online (Easiest)

Visit the hosted version at: [https://cfurrow7.github.io/dx7-opxy/tv7.html](https://cfurrow7.github.io/dx7-opxy/tv7.html)

### Local Development

```bash
# Clone the repository
git clone https://github.com/cfurrow7/dx7-opxy.git
cd dx7-opxy

# Install dependencies
npm install

# Start local server
npm start
```

Then open http://localhost:8080/tv7.html in your browser.

## Usage

1. **Load a DX7 Bank**
   - Upload your own .syx file, or
   - Select from 50+ included example banks

2. **Select a Patch**
   - Click any patch from the list
   - The output name will auto-populate as "DX7 [PatchName]"

3. **Configure Parameters**
   - **Output Format**: Choose Tonverk or OP-XY
   - **Key-On Duration**: How long to hold each note (default: 2000ms)
   - **MIDI Note Range**: Min/Max notes and increment
   - Preview notes using the on-screen keyboard

4. **Download**
   - Click "Download Multisample"
   - **Tonverk**: Generates a .zip with .elmulti + .wav
   - **OP-XY**: Generates a .preset.zip ready to load

## OP-XY Format

The OP-XY export creates a `.preset` folder containing:
- Individual WAV files for each sampled note (16-bit PCM)
- **Automatic silence trimming** (-60dB threshold) for tight, clean samples
- `patch.json` with proper OP-XY v4 format specifications:
  - MIDI key mapping with velocity layers
  - Loop points and crossfade settings
  - Envelope, LFO, and FX parameters
  - Region mapping across the keyboard

## Example Patches Included

- Tyler's Favorites
- Legowelt Magic DX7 Cart
- Rhodes, Wurlitzer, Clavinets
- ROM Banks 1A-4B
- PPG Vocal, Deckard
- And 40+ more!

## Technical Details

### DX7 Synthesis Engine
- Pure JavaScript implementation
- Based on Mutable Instruments Plaits DX7/FM engine
- 6 operators, 32 algorithms
- Envelope and LFO modulation
- Normalized to 0.5 dBFS for polyphonic stacking

### Output Specifications
- Sample Rate: 44.1kHz
- Bit Depth: 32-bit float (internal) → 16-bit PCM (export)
- Format: Mono WAV files
- Automatic silence trimming (OP-XY only): -60dB threshold removes leading/trailing silence

## License

MIT License - see original [spacejam/tv7-js](https://github.com/spacejam/tv7-js) for attribution.

## Credits

- Original TV7 tool by [Tyler Neely](https://github.com/spacejam) - Foundation for Tonverk export
- DX7 synthesis engine ported from [Mutable Instruments Plaits](https://mutable-instruments.net/)
- OP-XY integration and 80s DX7 interface design by Chad Furrow

## Links

- [OP-XY Multisample Converter](https://github.com/cfurrow7/opxy-converter) - Convert existing multisamples to OP-XY format
- [Original TV7 Tool](https://github.com/spacejam/tv7-js) - Tonverk-only version
- [DX7 SYSEX Patches](http://www.dxsysex.com/) - Large collection of DX7 patches
