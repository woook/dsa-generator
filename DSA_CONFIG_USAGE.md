# Data Sharing Agreement - YAML Configuration Guide

## Overview

The DSA generator script is now fully configurable via YAML files. This allows you to create different Data Sharing Agreements for various projects by simply editing a configuration file.

## Usage

### Generate with default config (Community Cloud):
```bash
source venv/bin/activate
python generate_east_genomics_dsa_pdf.py
```

### Generate with custom config:
```bash
source venv/bin/activate
python generate_east_genomics_dsa_pdf.py --config your_config.yaml
```

## YAML Configuration Structure

### Header
```yaml
header:
  title: "Data Sharing Agreement"  # Main title in document header
```

### Document Details
```yaml
document_details:
  title: "Project Name Data Sharing Agreement"
  reference_label: "Bioinformatics Document Reference"
  reference_tooltip: "Tooltip for the reference field"
```

### Document Control
```yaml
document_control:
  heading: "Document control"
  text: "Document control statement..."
```

### Main Content Sections

Sections support:
- **Plain paragraphs** (strings)
- **Subsections** (with `subsection_title` and nested `content`)
- **Bullet lists** (with `bullets` array)

```yaml
sections:
  - title: "1. Section Title"
    content:
      - "Plain paragraph text"
      - subsection_title: "1.1 Subsection"
        content:
          - "Subsection paragraph"
          - bullets:
              - "Bullet point 1"
              - "Bullet point 2"
          - "Another paragraph"
      - bullets:
          - "<b>Bold bullet</b> — with description"
          - "Regular bullet"
```

### Participant Declaration
```yaml
declaration:
  title: "9. Participant Declaration"
  text: "Declaration text..."
  fields:
    - label: "Full Name"
      name: "fullName"
      tooltip: "Enter your full name"
    - label: "Job Title"
      name: "jobTitle"
      tooltip: "Enter your job title"
  footer_text: "Retention statement..."
```

### Footer and Metadata
```yaml
footer:
  text: "Footer text for each page"

metadata:
  pdf_title: "PDF document title"
  pdf_author: "PDF author"
```

## Creating a New DSA for a Different Project

1. **Copy the template**:
   ```bash
   cp dsa_config_community_cloud.yaml dsa_config_my_project.yaml
   ```

2. **Edit the configuration**:
   - Update project-specific text
   - Modify section titles and content
   - Add or remove sections as needed
   - Adjust declaration fields

3. **Generate the documents**:
   ```bash
   python generate_east_genomics_dsa_pdf.py --config dsa_config_my_project.yaml
   ```

## Tips

- **HTML in text**: You can use `<b>` tags for bold text in PDF (automatically stripped in DOCX)
- **Long text**: YAML supports multi-line strings with proper line breaking
- **Structure**: Maintain the nesting structure for subsections to render correctly
- **Validation**: Test your config with a quick generation to verify formatting

## Files

- `dsa_config_community_cloud.yaml` - Original Community Cloud DSA configuration
- `dsa_config_test.yaml` - Example test configuration showing customization
- `generate_east_genomics_dsa_pdf.py` - Main generator script
- Output files: `east_genomics_data_sharing_agreement.pdf` and `.docx`

## Benefits

- **Easy Updates**: Change content without touching Python code
- **Version Control**: Track different project configs separately
- **Non-Technical Editing**: YAML is more accessible than Python
- **Template Reuse**: Copy and modify configs for new projects
- **Documentation**: YAML file serves as clear documentation
