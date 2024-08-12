# Peralta CCD Flex Day Panel "AI: Where Are We Now?" Resource Annotation Script

## Overview

This repository contains scripts developed to support the Peralta Community College District (PCCD) Flex Day panel titled "AI: Where Are We Now?", scheduled for August 15, 2024. The list of resources (`resources_in.tsv`) was compiled to provide faculty and staff with valuable AI-related materials that can be utilized for professional development.

## Project Description

### Purpose

The purpose of this project is to annotate a list of AI-related resources by automatically generating descriptions and extracting relevant keywords. The output is intended to facilitate easier categorization and access to AI resources for PCCD faculty and staff.

### Scripts

1. **Resource Annotation Script** (`annotate_resources.py`):
    - **Input**: The script reads in a TSV file named `resources_in.tsv` which contains three columns: 'Soft Label', 'Title', and 'URL'.
    - **Processing**:
        - The script uses OpenAI's GPT-4 to generate descriptions of each resource by analyzing the title and the URL.
        - It classifies the type of media (e.g., PDF, YouTube Video, Web Page) based on the URL and stores this classification in a new column called `Media Type`.
        - The script then processes the 'Description' column to extract keywords based on specific patterns found in the description (e.g., "**Keywords:**").
    - **Output**: The final annotated resource list is saved as `resource_anno3.tsv`, with additional columns for `Description`, `Media Type`, and `Keywords`.

2. **Key Components**:
    - **GPT-4 Integration**: The script uses OpenAI's GPT-4 model to generate resource descriptions. Ensure that you have access to GPT-4 through an API key.
    - **Environment Variable**: The OpenAI API key must be set as an environment variable (`OPENAI_API_KEY`) to run the script successfully.

### How to Use

1. **Clone the Repository**:
    ```
    git clone https://github.com/yourusername/peralta-ai-resources.git
    cd peralta-ai-resources
    ```

2. **Set Up the Environment**:
    - Ensure that Python 3.x is installed.
    - Install the necessary packages:
        ```
        pip install openai
        ```

3. **Set the OpenAI API Key**:
    - Set your OpenAI API key as an environment variable:
        - **Linux/Mac**:
            ```bash
            export OPENAI_API_KEY="your-api-key-here"
            ```
        - **Windows**:
            ```bash
            set OPENAI_API_KEY="your-api-key-here"
            ```

4. **Run the Script**:
    - To process the resources and generate the annotated file:
      ```bash
      python annotate_resources.py
      ```

5. **Output**:
    - The output will be saved as `resource_anno3.tsv` with annotated descriptions, media types, and keywords.

### Repository Contents

- **`resources_in.tsv`**: The input file containing the initial list of AI-related resources.
- **`annotate_resources.py`**: The Python script that processes the resources and generates the annotated file.
- **`resource_anno3.tsv`**: The output file containing the annotated resources.
- **`README.md`**: This file, providing an overview and instructions.

### Additional Information

- **Contributors**: If there are any contributors to the project, list them here.
- **License**: Specify the license under which the project is released.
- **Issues**: For issues or feature requests, please open a ticket in the repository's issue tracker.

---

If you have any other details you'd like to include (e.g., contributors, specific versions of Python or packages, licensing information), please let me know!
