# Ubuntu ISO Customized Later 🐧

A GitHub Actions-powered Ubuntu ISO builder designed to give us a clean base that we can customize over time.

## 🚀 What it does

This repository automatically builds a bootable Ubuntu live ISO using GitHub Actions.

The current build is based on **Ubuntu 24.04 LTS (Noble)** and includes a basic set of useful applications and development tools.

Every build produces:

- `carson-ubuntu-custom.iso` — the bootable ISO
- `carson-ubuntu-custom.iso.sha256` — SHA-256 checksum for verification

## 🛠️ Customization

The repository is intentionally structured so we can keep adding features later.

### Packages

Add Ubuntu packages to:

```text
config/packages.list.chroot
```

Use one package name per line.

### Hooks

Add executable `.hook.chroot` scripts to:

```text
config/hooks/
```

These can be used later for things like:

- Installing additional software
- Changing system settings
- Creating users or configuration files
- Applying desktop customizations
- Running setup commands inside the ISO

### Custom files

Files placed under:

```text
config/includes.chroot/
```

are copied into the ISO's filesystem while it is being built.

## ⚙️ GitHub Actions

The workflow is located at:

```text
.github/workflows/build-ubuntu-iso.yml
```

It can run automatically when the build configuration changes or manually through **GitHub Actions → Build Custom Ubuntu ISO → Run workflow**.

The build runs on a GitHub-hosted Ubuntu 24.04 runner, so no self-hosted runner or VM is required.

## 📁 Repository layout

```text
.
├── .github/
│   └── workflows/
│       └── build-ubuntu-iso.yml
├── config/
│   ├── hooks/
│   ├── includes.chroot/
│   └── packages.list.chroot
└── README.md
```

## 🎯 Future plans

This project is meant to be a starting point rather than a finished distro. Future customization can include:

- 🎨 Desktop/theme customization
- 📦 More applications and development tools
- ⚙️ Custom system configuration
- 🖥️ Custom desktop defaults
- 🧰 Custom scripts and utilities
- 🔧 More automated ISO customization
- 📀 Additional boot and installer improvements

## 📜 License

No license has been selected for this project yet.
