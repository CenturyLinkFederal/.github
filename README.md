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
```

## AI Adoption Tracking

The `create-copilot-instructions.yml` template includes integrated AI adoption tracking via git hooks. This system automatically detects and tags AI-assisted commits across repositories.

### How It Works

**Files Created by Template:**
- `.github/copilot-instructions.md` — Developer guidance document with repository-specific setup
- `.githooks/prepare-commit-msg` — Auto-tagging git hook (runs on every commit)

**Signal Detection:**
The hook automatically detects AI-assisted commits using multiple signals:
- GitHub Copilot co-author metadata
- Explicit keywords: `copilot`, `ai-assisted`, `@copilot`, `gpt`, `claude`, `cursor`
- Implicit patterns and tool signatures

**Tag Format:**
Detected commits are automatically tagged with the `[AI-ASSISTED]` prefix:
```bash
# Developer commits with Copilot
git commit -m "Copilot: Add authentication endpoint"

# Hook auto-tags it:
# [AI-ASSISTED] Copilot: Add authentication endpoint
```

### Developer Setup

The setup process depends on the project type:

**For Node.js Projects:**

When you run `npm install` or `npm ci`, the hook setup is automatic:

```bash
npm install  # Git hooks are configured automatically
```

The `postinstall` and `prepare` scripts in `package.json` handle it. Verify:
```bash
git config core.hooksPath  # Should return: .githooks
```

**For Non-Node Projects (Java, Python, etc.):**

Run the setup script once after cloning:

```bash
./setup-dev-env.sh
```

This script configures git hooks and any other project-specific setup. Verify:
```bash
git config core.hooksPath  # Should return: .githooks
```

### Why Custom Hook Path?

Git hooks are normally stored in `.git/hooks/` (not committed to version control). By using `.githooks/` as a custom path, the hook file can be:
- ✅ Committed to the repository
- ✅ Distributed to all clones automatically
- ✅ Updated when the repo is pulled

The `git config core.hooksPath .githooks` command makes git aware of this custom location.

### Setup Automation Strategies

This template supports two complementary approaches to ensure developers don't have to manually run `git config`:

**Node Projects (Approach A):**
- Add `postinstall` and `prepare` scripts to `package.json`
- Hook setup runs automatically when developers run `npm install` or `npm ci`
- Zero developer friction—no extra steps needed

**Non-Node Projects (Approach B):**
- Create `./setup-dev-env.sh` in the `.githooks` folder
- Include it in README with clear "Run this first" instructions
- Can bundle other project-specific setup steps
- Explicit developer action, but documented and simple

### AI Adoption Metrics

The `comprehensive-codebase-review.yml` template automatically:
- Scans commits for `[AI-ASSISTED]` tags
- Records the signal type (hook, explicit keyword, metadata, etc.)
- Recovers individual commits from squash-merge workflows
- Generates adoption metrics in `copilot-eval/ai-adoption.md` and `.csv` files

### Applying to Multiple Repositories

**Per Repository:**
1. Copy `.github/ISSUE_TEMPLATE/create-copilot-instructions.yml` to target repo
2. Open the issue: "New Issue" → "Create Copilot Instructions"
3. Copilot generates `.github/copilot-instructions.md` and `.githooks/prepare-commit-msg`
4. Commit both files to the repo
5. Developers run: `git config core.hooksPath .githooks`

**At Scale:**
- Use a repository template that includes the issue template
- All new repos get AI tracking automatically
- Existing repos can adopt via the issue template workflow

### No Setup Scripts Needed

The system is designed for simplicity:
- No separate `setup-ai-hooks.sh` script required
- The issue template creates files directly
- Files are committed and distributed with clones
- Developers only run one command: `git config core.hooksPath .githooks`
