# din5008-templates
[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa] [![status: experimental](https://github.com/GIScience/badges/raw/master/status/experimental.svg)](https://github.com/GIScience/badges#experimental)

A collection of DIN5008 compliant envelope templates made in LaTeX and rendered as PDF. These templates follow the envelope dimensions specified in DIN 680.

## About the project
This project addresses the challenge of creating dimensionally accurate, DIN-compliant envelope templates. I could not find precise, reliable templates and got frustrated enough to give it a shot.

## Support
The following table shows the current implementation status of envelope formats:

Symbols:
- ✅ existing
- ⚠️ work in progress
- ❌ not supported yet.

| Format  | Windowless | Window | filename |
| ------- | ---------- | ------ | -------- |
| C6 | ❌ | ❌ | N/A |
| B6 | ❌ | ❌ | N/A |
| DL | ⚠️ | ❌ | N/A |
| C6/C5 | ❌ | ❌ | N/A |
| C5 | ❌ | ❌ | N/A |
| B5 | ❌ | ❌ | N/A |
| C4 | ❌ | ❌ | N/A |
| B4 | ❌ | ❌ | N/A |
| E4 | ❌ | ❌ | N/A |

## Generating Previews
To generate the PNG previews of the rendered PDF documents, this command can be used (requires image magick).
```sh
find ./templates -type f -name "*.pdf" -exec sh -c '
  for pdf; do
    rel_path=${pdf#./templates/}
    dir_path="./examples/$(dirname "$rel_path")"
    mkdir -p "$dir_path"
    magick -density 150 "$pdf" "$dir_path/$(basename "${pdf%.pdf}.png")"
  done
' sh {} +
```

## License
This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
