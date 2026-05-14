# Browser MML Player

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A simple Music Macro Language (MML) player that runs in the browser, powered by the Web Audio API.


![Demo page screenshot showing a large text area with MML code, and Play/Stop buttons.](https://user-images.githubusercontent.com/164197/188283422-90176884-6997-4059-994c-2831518f972b.png)


## Demos

- **[Live Demo](https://t-sin.github.io/browser-mml-player/)**: Try the player with editable MML code.
- **[Xmas Demo](https://code4fukui.github.io/browser-mml-player/player.html)**: A pre-loaded MML performance.

## Features

- **In-Browser Playback**: Parses and plays MML directly in the browser using the Web Audio API.
- **Multi-Track Support**: Compose music with multiple simultaneous tracks, separated by `---`.
- **Sound Control**: Adjust parameters for each track independently.
  - `@volume`: Controls the track's volume (e.g., `@volume=0.5`).
  - `@pan`: Controls the stereo panning (-1.0 for left, 1.0 for right).
  - `@pitch`: Applies a frequency offset in Hz.
- **Tempo Control**: Set the global tempo using `@sys.bpm` (beats per minute).
- **Simple Waveform**: Generates sound using a square wave `OscillatorNode`.

## MML Syntax

The player supports a simple MML syntax. Tokens are separated by spaces or newlines.

| Command | Syntax | Description | Example |
| :--- | :--- | :--- | :--- |
| **Note** | `[cdefgab][0-9][+-]?:[0-9]+` | Plays a note. Format is `(note)(octave)(sharp/flat):(length)`. | `c4:4`, `f+5:8` |
| **Rest** | `r:[0-9]+` | A period of silence. | `r:4` |
| **Tie** | `=:[0-9]+` | Continues the previous note for a new duration. | `c4:4 =:8` |
| **Track Separator** | `---` | Separates MML for different tracks. | `c4:4 --- e4:4` |
| **Parameter** | `@name=value` | Sets a parameter for the current track. | `@volume=0.3` |

## Local Development

To run the player on your local machine:

1.  **Prerequisites**: You need [Node.js](https://nodejs.org/) and npm installed.

2.  **Clone and Install**:
    ```sh
    git clone https://github.com/t-sin/browser-mml-player
    cd browser-mml-player
    npm install
    ```

3.  **Run the Development Server**:
    ```sh
    npm start
    ```

4.  Open your browser and navigate to `http://localhost:1234`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.