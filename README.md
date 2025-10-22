\# DevOps Assignment 7 - Automated LaTeX Compilation



\*\*Author:\*\* Akshay Kumar (Group 13)  

\*\*Domain:\*\* devops-13-overleaf.me  

\*\*Repository:\*\* https://github.com/AkshayKumarTN/overleaf-devops13



\## Overview

This project implements automated LaTeX document compilation using GitHub Actions. Every push triggers automatic compilation, version tracking, and PDF storage.



\## Features

\- ✅ Automatic compilation on git push

\- ✅ Changelist-based version numbering (CL###-hash)

\- ✅ GitHub-hosted runner compilation

\- ✅ Self-hosted runner on Overleaf server

\- ✅ PDF storage in repository

\- ✅ ZIP archives as artifacts

\- ✅ Docker containerized runner



\## Quick Start



\### View Latest PDF

\- \*\*Cloud-compiled:\*\* \[compiled-pdfs/main-latest.pdf](compiled-pdfs/main-latest.pdf)

\- \*\*Local-compiled:\*\* \[local-compiled/](local-compiled/)



\### Compile Locally

```bash

pdflatex main.tex

pdflatex main.tex  # Run twice for references

```



\## Workflows



\### 1. Cloud Compilation (`compile-latex.yml`)

\- Runs on GitHub-hosted Ubuntu runners

\- Compiles on every `.tex` file change

\- Uploads PDF as artifact

\- Creates releases with version tags



\### 2. Commit to Repo (`compile-and-commit.yml`)

\- Compiles and commits PDF back to repository

\- Maintains `compiled-pdfs/` directory

\- Creates ZIP archives

\- Updates changelog



\### 3. Local Runner (`compile-local-runner.yml`)

\- Runs on self-hosted Overleaf server

\- Faster compilation

\- Stores in `local-compiled/` directory



\## Version Format

```

Version: CL42-a1b2c3d (2025-10-22)

```

\- `CL42`: Changelist 42 (42nd commit)

\- `a1b2c3d`: Git commit hash

\- `2025-10-22`: Commit date



\## Project Structure

```

overleaf-devops13/

├── main.tex                    # Main LaTeX document

├── version.tex                 # Auto-generated version info

├── .github/workflows/          # GitHub Actions workflows

├── compiled-pdfs/              # Cloud-compiled PDFs

├── local-compiled/             # Self-hosted compiled PDFs

├── Dockerfile.runner           # Docker image for runner

└── README.md                   # This file

```



\## Setup Instructions



\### Prerequisites

\- GitHub account

\- Domain: devops-13-overleaf.me

\- Server with Docker (for self-hosted runner)

\- LaTeX distribution (for local compilation)



\### GitHub Actions Setup

1\. Fork/clone this repository

2\. Push changes to trigger workflows

3\. Check Actions tab for build status

4\. Download PDFs from Artifacts or compiled-pdfs/



\### Self-Hosted Runner Setup

See \[RUNNER\_SETUP.md](RUNNER\_SETUP.md) for detailed instructions.



\## Testing

Make changes to `main.tex` and push:

```bash

git add main.tex

git commit -m "Test automatic compilation"

git push origin main

```



Check the Actions tab to see workflows running.



\## Artifacts

\- \*\*PDF Files:\*\* Available in Actions → Workflow → Artifacts

\- \*\*Releases:\*\* Tagged releases with attached PDFs

\- \*\*Repository:\*\* PDFs committed to `compiled-pdfs/` directory



\## Domain Configuration

\- \*\*Domain:\*\* devops-13-overleaf.me

\- \*\*Overleaf URL:\*\* https://overleaf.devops-13-overleaf.me (when configured)

\- \*\*SSL:\*\* Let's Encrypt (auto-renewal)



\## Technologies Used

\- LaTeX (texlive-full)

\- GitHub Actions

\- Docker

\- Ubuntu 22.04

\- nginx-proxy + acme-companion



\## License

Educational project for DevOps course.



\## Contact

\- GitHub: \[@AkshayKumarTN](https://github.com/AkshayKumarTN)

\- Repository: \[overleaf-devops13](https://github.com/AkshayKumarTN/overleaf-devops13)

