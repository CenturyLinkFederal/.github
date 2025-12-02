# .github

This repository contains organization-wide community health files for all repositories under the CenturyLinkFederal organization.

## Issue Templates

This repository provides default issue templates that will be available to all repositories in the CenturyLinkFederal organization that don't have their own issue templates.

### Available Templates

- **🐛 Bug Report** (`bug_report.yml`) - For reporting bugs or unexpected behavior
- **🚀 Feature Request** (`feature_request.yml`) - For suggesting new features or enhancements
- **📚 Documentation** (`documentation.yml`) - For reporting documentation issues or suggesting improvements
- **❓ Question** (`question.yml`) - For asking questions about the project

### How It Works

GitHub automatically makes these templates available to all repositories in the organization that don't have their own `.github/ISSUE_TEMPLATE` directory. When users create a new issue in any repository, they'll see these templates as options.

### Customizing Templates

Individual repositories can override these organization-wide templates by creating their own `.github/ISSUE_TEMPLATE` directory with custom templates.

### Configuration

The `config.yml` file in `.github/ISSUE_TEMPLATE/` controls:
- Whether blank issues are enabled
- Contact links that appear in the issue template chooser

For more information, see [GitHub's documentation on creating issue templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository).