# GitHub Issue Templates Repository

A collection of reusable GitHub issue templates designed to standardize and streamline common development workflows, code reviews, and quality improvements across repositories.

## Overview

This repository contains pre-configured GitHub issue templates that can be easily adopted in any project. These templates ensure consistent documentation, thorough analysis, and clear expectations for various development tasks.

## Available Templates

### 1. Create Copilot Instructions
**File:** `.github/ISSUE_TEMPLATE/create-copilot-instructions.yml`

Generate comprehensive `copilot-instructions.md` files based on codebase analysis. This template helps document:
- Coding standards and architectural patterns
- Test coverage requirements
- Linting and formatting rules
- Contribution guidelines

### 2. Comprehensive Codebase Review
**File:** `.github/ISSUE_TEMPLATE/comprehensive-codebase-review.yml`

Request a thorough evaluation of your entire codebase including:
- Code quality and best practices assessment
- Architectural documentation and diagrams
- API and library dependency inventories
- CI/CD pipeline health analysis
- Modernization recommendations
- Scoring system (1-10 scale) across 10 categories
- All deliverables organized in a `copilot-eval/` folder

### 3. Improve Test Coverage
**File:** `.github/ISSUE_TEMPLATE/improve-test-coverage.yml`

Drive test coverage improvements with clear goals:
- Target 80% coverage across statements, branches, functions, and lines
- Supports Playwright and other testing frameworks
- Before/after coverage reporting requirements
- Structured acceptance criteria

### 4. Improve Test Coverage (Java)
**File:** `.github/ISSUE_TEMPLATE/improve-test-coverage-java.yml`

Focus on Java repositories that rely on JUnit:
- Emphasizes achieving at least 80% coverage with JUnit and Mockito support
- Requires documenting before/after coverage metrics in the PR description
- Highlights critical path testing plus refactoring existing tests when needed
- Provides detailed task list tailored to Java-specific edge cases

## How to Use

### Option 1: Copy to Your Repository

1. Copy the desired template file(s) to your repository's `.github/ISSUE_TEMPLATE/` directory
2. Commit and push the changes
3. Create a new issue in your repository - you'll see the templates available

### Option 2: Direct Implementation

```bash
# Clone this repository
git clone https://github.com/YOUR_USERNAME/.github.git

# Copy templates to your target repository
cp -r .github/ISSUE_TEMPLATE /path/to/your/repository/.github/

# Commit in your target repository
cd /path/to/your/repository
git add .github/ISSUE_TEMPLATE
git commit -m "Add GitHub issue templates"
git push
