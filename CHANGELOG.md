# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.9.0] - 2025-01-27

### Added
- Support for Python 3.11 and 3.12
- New `requirements-updated.txt` with clean dependency list
- Comprehensive upgrade guide (`UPGRADE_NOTES.md`)
- TensorFlow 2.x compatibility layer

### Changed
- **BREAKING**: Minimum Python version is now 3.8 (Python 3.7 support removed)
- Updated all core dependencies to latest versions:
  - requests: 2.20.0 → 2.31.0
  - opencv-python: 4.2.0.32 → 4.8.0.0
  - tqdm: 4.23.0 → 4.66.0
  - arabic-reshaper: 2.1.3 → 3.0.0
- Upgraded TensorFlow from 1.x to 2.x:
  - tensorflow: 1.13.1 → 2.20.0
  - numpy: removed version restriction (<1.17 → >=1.24.0)
  - matplotlib: 3.0.2 → 3.7.0
  - seaborn: 0.9.0 → 0.12.0
- Improved matplotlib buffer handling for better compatibility

### Fixed
- TensorFlow 2.x compatibility issues in handwritten text generation
- Deprecated `matplotlib.mlab` import removed
- Better error handling for TensorFlow model loading

### Security
- Removed Python 3.7 support due to security concerns
- Updated all dependencies to latest secure versions

## [1.8.0] - Previous Release
- Previous stable release with older dependencies