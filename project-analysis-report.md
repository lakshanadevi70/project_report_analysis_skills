# Project Analysis Report

## Executive Summary

This repository is a small prototype for an AI-powered career mentoring application built with Python and Streamlit. The current implementation allows a user to upload a resume PDF, extract text from it, and display a career-oriented report. The codebase is lightweight and easy to follow, but the core analysis logic is still largely hardcoded rather than derived from the uploaded resume content.

## 1. Project Purpose

The project appears intended to help users receive career guidance based on their resume. In its current form, the flow is:

1. A user uploads a PDF resume through the Streamlit interface.
2. The application extracts text from the PDF.
3. The extracted text is passed into a reporting function.
4. A predefined report is returned to the user.

The repository is therefore better described as a prototype demo than a fully functional resume-analysis system.

## 2. Project Type and Scope

This is a Python-based desktop/web-style prototype with:
- a frontend-style UI built with Streamlit,
- a small modular Python backend structure,
- a few helper modules for recommendations and roadmap generation,
- no visible database layer, authentication layer, or production deployment setup.

## 3. Confirmed Technology Stack

### Runtime and app framework
- Python
- Streamlit

### Libraries and packages
- PyMuPDF via the fitz module for PDF extraction
- python-dotenv for environment configuration
- google-generativeai for Gemini API integration

### Dependency manifest
- [requirements.txt](requirements.txt)

## 4. Repository Structure

The repository is organized into a few clear areas:

- [app.py](app.py) — Streamlit UI entry point
- [agents/career_agent.py](agents/career_agent.py) — Career report generation logic
- [skills/resume_analyzer.py](skills/resume_analyzer.py) — PDF text extraction
- [skills/project_recommender.py](skills/project_recommender.py) — Project recommendation logic
- [skills/internship_recommender.py](skills/internship_recommender.py) — Internship recommendation logic
- [skills/roadmap_generator.py](skills/roadmap_generator.py) — Roadmap generation logic
- [hooks/upload_hook.py](hooks/upload_hook.py) — Example upload-related hook snippet
- [test.py](test.py) — Environment and Gemini configuration check

## 5. Architecture Overview

The code follows a simple modular architecture:

- The UI layer lives in [app.py](app.py).
- Resume parsing is isolated in [skills/resume_analyzer.py](skills/resume_analyzer.py).
- Analysis/report generation is isolated in [agents/career_agent.py](agents/career_agent.py).
- Supporting recommendation helpers are kept in the skills folder.

This is a clean prototype structure, but the modules are not deeply integrated. The current report generation is not yet using the resume text in a meaningful way.

## 6. Features Present

### Implemented
- Resume upload through a Streamlit file uploader
- PDF text extraction
- Career report output
- Project and internship recommendation helper functions
- Roadmap generation helper functions

### Not implemented or incomplete
- Real resume parsing into structured fields such as skills, experience, education, or certifications
- True semantic analysis of uploaded content
- Authentication or user accounts
- Persistent storage or history
- Automated tests for the core workflow

## 7. Code Quality Observations

### Strengths
- The repository is compact and easy to understand.
- The main responsibilities are separated into understandable modules.
- The code uses straightforward Python patterns and does not appear overly complex.

### Issues
- The core analysis function in [agents/career_agent.py](agents/career_agent.py) returns a fixed report instead of processing the incoming resume text.
- The app path in [app.py](app.py) passes the uploaded resume content into a function that does not use it.
- The repository contains a second module named [skills/career_agent.py](skills/career_agent.py) that appears to focus on environment configuration rather than the app’s main analysis flow, which can be confusing.
- The current project is still mostly demo-oriented and not yet production-ready.

## 8. Security and Configuration Notes

### What is present
- The project uses environment variables for the Gemini API key through [test.py](test.py) and [skills/career_agent.py](skills/career_agent.py).
- The code does not appear to hardcode secrets directly.

### Gaps
- There is no visible input validation beyond the file uploader configuration.
- There is no obvious authentication or authorization model.
- The code depends on external API configuration, but there is no clear user-facing error handling for missing credentials.

## 9. Dependencies and External Services

The main external dependency is the Gemini API, which is referenced through the google-generativeai package. The repository also depends on Streamlit and PyMuPDF for the main workflow.

No database service or API backend is present in the current repository structure.

## 10. Testing and Validation

No meaningful automated test suite was found for the core application behavior. The file [test.py](test.py) appears to be a simple environment check and does not validate the resume flow or report generation.

## 11. Recommendations

1. Replace the hardcoded report output in [agents/career_agent.py](agents/career_agent.py) with real analysis of the uploaded resume content.
2. Parse resume text into structured sections such as skills, experience, and education.
3. Add validation for empty or invalid PDF uploads.
4. Add proper error handling for missing API keys and failed API calls.
5. Introduce a small automated test suite for the extraction and report-generation flow.
6. Decide whether the project should remain a prototype or evolve into a fuller product with persistence, authentication, and deployment support.

## 12. Conclusion

The project is a clear and approachable prototype for an AI career mentor, but it is not yet a true resume-analysis application. Its main next step is to connect the uploaded resume data to real analysis logic instead of returning a static report.
