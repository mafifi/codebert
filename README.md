# CodeBERT PR Embedding Analysis

This project fetches code changes from GitHub pull requests, computes embeddings using an LMStudio model (based on CodeBERT), and helps you analyze or store those embeddings.

## Prerequisites

- **Python**: 3.9 or higher
- **Git**: for cloning this repo
- **GitHub Personal Access Token**: to access pull request data
- **LMStudio API URL & Key**: for embedding service

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/codebert.git
   cd codebert
   ```

2. Create a `.env` file in the project root containing your environment variables:
   ```bash
   cat > .env <<EOF
   GITHUB_TOKEN=your_github_token_here
   LMSTUDIO_API=https://api.your-lmstudio-instance.com
   EOF
   ```

3. Create and activate a virtual environment:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate  # on zsh/bash
   ```

4. Upgrade `pip` and install dependencies:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

5. Install Git hooks (runs nbstripout on every commit):
   ```bash
   pip install pre-commit
   pre-commit install

## Usage

1. Launch Jupyter (Lab or Notebook) and open `analysis.ipynb`:
   ```bash
   jupyter notebook analysis.ipynb
   ```

2. Configure the repository and pull request settings in the first cells (e.g., set `repo = gh.get_repo("owner/repo")`).
3. Run through the notebook cells to fetch PR diffs, generate embeddings, and inspect or store results.

## Customization

- To change the target repository, update the `get_repo` call in the notebook.
- To switch embedding models, modify the `model` field in the embedding request.

## Trouble-Shooting

- If you see authentication errors, ensure your `GITHUB_TOKEN` is valid and has appropriate scopes (repo access).
- Check that `LMSTUDIO_API` points to a reachable endpoint.
- Make sure your Python version is compatible (>=3.9).

---
*Happy coding!*