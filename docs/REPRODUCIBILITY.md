# Reproducibility and visual sources

## Scope

This guide describes what is available in the committed project and what is required to reproduce it. The documentation update inspected source and saved outputs; it did not rerun model training or hardware/simulation experiments.

## Required inputs

Several controller variants contain machine-specific absolute paths for gesture models and command files. Update them to the extracted paths and check model input dimensions and label ordering. Verify which controller a world assigns to its robot; not every bundled world is a complete drone demo. Camera-driven controllers need a working webcam.

## Entry point

Extract `Robotics.zip` locally. The archive's world header identifies **Webots R2023b**. Review the extracted `cutchesta/worlds/` and controller directories before opening a world in a compatible Webots installation.

Configure Webots to use a Python environment containing the controller's imported packages, including OpenCV, NumPy, MediaPipe, and TensorFlow where required. The `controller` module comes from Webots, rather than a generic pip package.

## Evidence and interpretation

The archive contains source, learned gesture-model files, saved frames, and world previews. The preview above is an original saved world preview from the archive, not a new simulation run. Controller integration, gesture accuracy, and flight behavior were not executed during documentation preparation.

## Visual provenance

All screenshots and experiment figures are tied to repository material. Workflow SVGs are explanatory illustrations. The full image inventory is in [assets/sources.json](assets/sources.json).

| Visual | Source |
| --- | --- |
| [overview.svg](assets/overview.svg) | New explanatory project-workflow diagram based on the committed source and documentation; not a screenshot or measured result. |
| [simulation.jpg](assets/simulation.jpg) | Robotics.zip, cutchesta/worlds/.forest_fire.jpg |

## Validation

```bash
python tools/check_docs.py
```

The standard-library checker validates README/docs local link destinations and SVG/PNG/JPEG headers. It makes no external requests and installs no project runtime dependencies. External web links, model accuracy, image semantics, and full application execution need separate review.

## Reproduction record

For a new experiment or demo, record the source commit, environment versions, data provenance and split, configuration, command/notebook order, and resulting artifacts. Only label a measurement as reproduced after completing that run. Keep credentials and restricted datasets outside version control.
