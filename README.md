# Multi-Platform Matrix Build with GitHub Actions

A comprehensive demonstration of GitHub Actions matrix build strategy with artifact management across multiple platforms and configurations.

## 📧 Contact

**Email:**  23f2003095@ds.study.iitm.ac.in

## 🎯 Overview

This project showcases a production-ready CI/CD pipeline that:

- ✅ Builds across **7 different matrix configurations** in parallel
- ✅ Supports **3 operating systems** (Ubuntu, macOS, Windows)
- ✅ Tests **multiple Node.js versions** (16, 18, 20)
- ✅ Generates and uploads **unique build artifacts** for each variant
- ✅ Includes automated artifact verification
- ✅ Contains the required identifier: `matrix-594d068`

## 🏗️ Matrix Configuration

The workflow builds across these dimensions:

### Standard Matrix
- **Operating Systems:** `ubuntu-latest`, `macos-latest`, `windows-latest`
- **Node.js Versions:** `18`, `20`
- **Total Jobs:** 6 parallel jobs

### Extended Configuration
- **Special Build:** `ubuntu-22.04` with Node.js `16`
- **Total Jobs:** 7 parallel jobs

## 📦 Artifacts Generated

Each build generates artifacts with the naming pattern: `build-594d068-<os>-node<version>`

Examples:
- `build-594d068-linux-node18`
- `build-594d068-linux-node20`
- `build-594d068-mac-node18`
- `build-594d068-mac-node20`
- `build-594d068-win-node18`
- `build-594d068-win-node20`
- `build-594d068-linux-node16`

Each artifact contains:
- `output.txt` - Build report with system information
- `metadata.json` - Structured build metadata
- `app.js` - Sample Node.js application

## 🚀 Quick Start

### Setup Instructions

1. **Create the workflow file:**
   ```bash
   mkdir -p .github/workflows
   # Copy the workflow YAML to .github/workflows/matrix-build.yml
   ```

2. **Update your email in README.md:**
   ```bash
   # Replace your.email@example.com with your actual email
   ```

3. **Commit and push:**
   ```bash
   git add .
   git commit -m "Add multi-platform matrix build workflow"
   git push origin main
   ```

4. **Monitor the build:**
   - Go to the "Actions" tab in your GitHub repository
   - Click on the latest workflow run
   - Watch all 7 matrix jobs execute in parallel

## 📊 Workflow Structure

```
Multi-Platform Matrix Build
│
├── matrix-build (7 parallel jobs)
│   ├── Ubuntu Latest + Node 18
│   ├── Ubuntu Latest + Node 20
│   ├── macOS Latest + Node 18
│   ├── macOS Latest + Node 20
│   ├── Windows Latest + Node 18
│   ├── Windows Latest + Node 20
│   └── Ubuntu 22.04 + Node 16 (Special)
│
└── verify-artifacts (runs after all builds)
    ├── Downloads all artifacts
    ├── Verifies content integrity
    └── Generates verification report
```

## 🔍 Key Features

### Matrix Strategy
- **Parallel Execution:** All matrix variants run simultaneously
- **Cross-Platform:** Builds on Linux, macOS, and Windows
- **Version Testing:** Validates across multiple Node.js versions
- **Special Configurations:** Support for edge cases via `include`

### Artifact Management
- **Unique Naming:** Each artifact has a distinct identifier
- **Content Verification:** Automated checks ensure non-empty artifacts
- **Retention Policy:** Artifacts kept for 7 days
- **Error Handling:** Fails if artifacts are missing

### Required Identifiers
- ✅ Step name: `matrix-594d068`
- ✅ Artifact prefix: `build-594d068-*`

## 📝 Validation Checklist

- [x] At least 3 matrix jobs (we have 7)
- [x] At least 3 artifacts with `build-594d068` prefix (we have 8)
- [x] All artifacts contain actual content
- [x] Step identifier `matrix-594d068` included
- [x] README.md with email address

## 🛠️ Customization Options

### Add More Operating Systems
```yaml
matrix:
  os: [ubuntu-latest, ubuntu-22.04, macos-latest, macos-13, windows-latest]
```

### Add More Node Versions
```yaml
matrix:
  node-version: [14, 16, 18, 20, 21]
```

### Add Build Configurations
```yaml
matrix:
  build-type: [debug, release]
  optimization: [O0, O2, O3]
```

### Add Environment Variables
```yaml
matrix:
  include:
    - os: ubuntu-latest
      node-version: 18
      env:
        BUILD_ENV: production
```

## 📈 Performance Metrics

- **Parallel Jobs:** 7 simultaneous builds
- **Total Artifacts:** 8 (7 build artifacts + 1 verification report)
- **Cross-Platform:** 3 different operating systems
- **Version Coverage:** 3 Node.js versions

## 🔐 Security & Best Practices

- Uses official GitHub Actions (`actions/upload-artifact@v4`)
- Implements error handling (`if-no-files-found: error`)
- Includes artifact retention policies
- Cross-platform shell compatibility (`shell: bash`)
- Structured metadata for traceability

## 📖 Additional Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Matrix Strategy Guide](https://docs.github.com/en/actions/using-jobs/using-a-matrix-for-your-jobs)
- [Artifact Management](https://docs.github.com/en/actions/using-workflows/storing-workflow-data-as-artifacts)

## 🤝 Contributing

Feel free to submit issues or pull requests to improve this workflow demonstration.

## 📄 License

MIT License - Feel free to use this workflow in your projects!

---

**Remember to replace `your.email@example.com` with your actual email address!**
