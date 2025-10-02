# spectrum-analyzer
A spectrum analyzer project using Python for signal processing and visualization.
# 🔬 Interactive Spectrum Analyzer

A comprehensive Python-based spectrum analysis tool for identifying chemical elements from spectroscope images. This tool provides automated calibration, error correction, peak detection, and element identification with professional PDF reporting.

![Spectrum Analysis Demo](https://img.shields.io/badge/Python-3.7+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)

## ✨ Features

### 🔧 **Interactive Setup**
- **One-time calibration** using reference lamp spectra
- **Error correction** with background subtraction
- **User-friendly prompts** with file validation
- **Batch processing** for multiple spectrum analysis

### 📊 **Advanced Analysis**
- **Automated peak detection** using scipy algorithms
- **Element identification** from comprehensive spectral database
- **Multi-element combination matching** 
- **Statistical scoring** for match confidence

### 📈 **Professional Output**
- **Interactive plots** with matplotlib
- **CSV data export** for further analysis
- **Multi-page PDF reports** with detailed results
- **Comprehensive element matching results**

### 🎯 **Supported Elements**
- Hydrogen, Helium, Sodium, Magnesium
- Calcium, Mercury, Neon, Argon
- Easily expandable database

## 🚀 Quick Start

### 1. **Installation**

#### Option A: Automatic Installation (Recommended)
```bash
# Download and run the installer
python install_dependencies.py
```

#### Option B: Manual Installation
```bash
pip install -r requirements.txt
```

#### Option C: Platform-Specific Scripts
**Windows:**
```batch
# Double-click or run:
install_spectrum_analyzer.bat
```

**Linux/Mac:**
```bash
chmod +x install_spectrum_analyzer.sh
./install_spectrum_analyzer.sh
```

### 2. **Run the Analyzer**
```bash
python spectrum_analyzer.py
```

### 3. **Follow the Interactive Setup**
1. **Error Correction Setup** (optional)
   - Upload background spectrum (spectroscope with no sample)
   - Used for noise reduction

2. **Calibration Setup** (required)
   - Choose reference element (Mercury, Hydrogen, etc.)
   - Upload calibration lamp spectrum image

3. **Analysis**
   - Upload spectrum images for analysis
   - View results automatically
   - Analyze multiple spectra with same calibration

## 📁 Project Structure

```
spectrum-analyzer/
├── spectrum_analyzer.py          # Main analysis program
├── install_dependencies.py       # Cross-platform installer
├── install_spectrum_analyzer.bat # Windows installer
├── install_spectrum_analyzer.sh  # Linux/Mac installer
├── requirements.txt              # Python dependencies
├── README.md                     # This file
├── LICENSE                       # MIT License
├── .gitignore                   # Git ignore rules
├── examples/                     # Example images and data
│   ├── sample_mercury_lamp.jpg
│   ├── sample_hydrogen_spectrum.jpg
│   └── sample_analysis_results.pdf
└── results/                      # Output directory (auto-created)
    ├── *.csv                    # Spectrum data files
    └── *.pdf                    # Analysis reports
```

## 🔬 How It Works

### 1. **Image Processing**
- Loads spectrum images using OpenCV
- Converts to grayscale and extracts 1D intensity profile
- Applies error correction (background subtraction)

### 2. **Calibration**
- Maps pixel positions to wavelengths using reference spectra
- Polynomial fitting for accurate wavelength conversion
- Supports multiple reference elements

### 3. **Peak Detection**
- Uses scipy's `find_peaks` with adaptive thresholding
- Filters peaks by intensity and distance
- Returns wavelength and intensity pairs

### 4. **Element Identification**
- Matches detected peaks to known spectral lines
- Calculates confidence scores for single elements
- Tests combinations of multiple elements
- Ranks results by statistical confidence

## 📊 Example Usage

```python
# The program is fully interactive, but here's the process:

# 1. First run - setup
python spectrum_analyzer.py
# -> Set up error correction (optional)
# -> Set up calibration with Mercury lamp
# -> Analyze first spectrum

# 2. Subsequent runs - analysis only  
python spectrum_analyzer.py
# -> Analyze new spectra (uses saved calibration)
```

## 📈 Output Files

### **CSV Data Files**
- Raw wavelength and intensity data
- Compatible with Excel and other analysis tools
- Format: `results/[filename]_spectrum.csv`

### **PDF Reports**
- Professional multi-page analysis reports
- Spectrum plots with labeled peaks
- Element identification results
- Statistical confidence scores
- Format: `results/[filename]_report.pdf`

## 🛠️ System Requirements

### **Python Version**
- Python 3.7 or higher
- pip package manager

### **Dependencies**
- **NumPy** (≥1.19.0) - Numerical computations
- **Pandas** (≥1.2.0) - Data manipulation
- **Matplotlib** (≥3.3.0) - Plotting and visualization  
- **SciPy** (≥1.6.0) - Signal processing
- **OpenCV** (≥4.5.0) - Image processing

### **Supported Platforms**
- ✅ Windows 10/11
- ✅ macOS 10.14+
- ✅ Linux (Ubuntu, CentOS, Debian, etc.)

## 📷 Supported Image Formats

- **JPEG** (.jpg, .jpeg)
- **PNG** (.png)
- **TIFF** (.tiff, .tif)
- **BMP** (.bmp)
- Any format supported by OpenCV

## 🔧 Advanced Configuration

### **Adding New Elements**
Edit the `SPECTRAL_DATABASE` in `spectrum_analyzer.py`:
```python
SPECTRAL_DATABASE = {
    "YourElement": [wavelength1, wavelength2, wavelength3],
    # ... existing elements
}
```

### **Adjusting Detection Parameters**
- **Peak threshold**: Modify `threshold` parameter in `detect_peaks()`
- **Peak matching tolerance**: Adjust `tolerance` in `match_elements()`
- **Calibration polynomial degree**: Change `degree` in `calibrate_with_lamp()`

## 🐛 Troubleshooting

### **Common Issues**

**"No peaks found in calibration spectrum"**
- Ensure calibration image has good contrast
- Check if image is properly focused
- Try adjusting peak detection threshold

**"OpenCV installation failed"**
- Try different OpenCV packages: `opencv-python`, `opencv-contrib-python`, `opencv-python-headless`
- On Linux: Install system dependencies first

**"File not found errors"**
- Use absolute file paths
- Ensure file extensions match exactly
- Check file permissions

### **Getting Help**
1. Check the error messages in the console
2. Ensure all dependencies are installed correctly
3. Try the examples in the `examples/` folder
4. Open an issue on GitHub with error details

## 🤝 Contributing

We welcome contributions! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### **Areas for Contribution**
- Additional spectral line databases
- New analysis algorithms
- GUI interface development
- Documentation improvements
- Bug fixes and optimization

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **SciPy** community for signal processing algorithms
- **OpenCV** team for image processing capabilities
- **Matplotlib** developers for visualization tools
- **NIST Atomic Spectra Database** for reference spectral lines

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/spectrum-analyzer/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/spectrum-analyzer/discussions)
- **Email**: your.email@example.com

## 📊 Project Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/spectrum-analyzer)
![GitHub forks](https://img.shields.io/github/forks/yourusername/spectrum-analyzer)
![GitHub issues](https://img.shields.io/github/issues/yourusername/spectrum-analyzer)
![GitHub last commit](https://img.shields.io/github/last-commit/yourusername/spectrum-analyzer)

---

**Made with ❤️ for the scientific community**