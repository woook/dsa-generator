# Data Sharing Agreement Generator

A configurable Python-based generator for Data Sharing Agreement documents in both PDF and DOCX formats with East Genomics branding.

## Features

- **YAML-Configured**: All content is configurable via YAML files
- **Dual Format Output**: Generates both PDF and DOCX versions
- **Professional Styling**: East Genomics branding with dual logo header
- **Interactive PDFs**: Fillable form fields in PDF output
- **Flexible Structure**: Supports sections, subsections, paragraphs, and bullet lists

## Installation

1. Create a virtual environment:
```bash
python3 -m venv venv
source venv/bin/activate
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Generate with default config (Community Cloud):
```bash
python generate_east_genomics_dsa_pdf.py
```

### Generate with custom config:
```bash
python generate_east_genomics_dsa_pdf.py --config your_config.yaml
```

## Configuration

See [DSA_CONFIG_USAGE.md](DSA_CONFIG_USAGE.md) for detailed documentation on YAML configuration structure and examples.

### Quick Start

1. Copy the example config:
```bash
cp dsa_config_community_cloud.yaml dsa_config_my_project.yaml
```

2. Edit the YAML file with your project-specific content

3. Generate documents:
```bash
python generate_east_genomics_dsa_pdf.py --config dsa_config_my_project.yaml
```

## File Structure

- `generate_east_genomics_dsa_pdf.py` - Main generator script
- `dsa_config_community_cloud.yaml` - Example configuration (Community Cloud DSA)
- `dsa_config_test.yaml` - Test configuration demonstrating customization
- `DSA_CONFIG_USAGE.md` - Detailed configuration guide
- `logo_east_genomics.png` - East Genomics logo (left)
- `logo_east_genomics_new` - Cambridge University Hospitals NHS logo (right)
- `requirements.txt` - Python dependencies

## Output

The script generates:
- `east_genomics_data_sharing_agreement.pdf` - PDF with fillable form fields
- `east_genomics_data_sharing_agreement.docx` - Word document version

## Requirements

- Python 3.x
- reportlab
- python-docx
- PyYAML

## License

East Genomics
