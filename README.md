

# Flutter Version Management (FVM) Setup Guide

This project uses **FVM (Flutter Version Management)** to manage and lock the Flutter SDK version at the project level. This ensures all developers and CI/CD pipelines use the same Flutter version.

---

## ✅ Step 1: Install FVM Globally

Run the following command to install FVM globally:

```bash
dart pub global activate fvm
```

After successful installation, verify it using:

```bash
fvm
```

You should see a list of available FVM commands like `install`, `list`, `use`, etc.

---

## ✅ Step 2: Check Installed Flutter SDKs

Before installing any Flutter version, check existing FVM SDKs:

```bash
fvm list
```

If no versions are installed, you will see:

```text
No SDKs have been installed yet.
```

---

## ✅ Step 3: View Available Flutter Releases

To see all available Flutter versions:

```bash
fvm releases
```

This shows all **stable, beta, and historical Flutter versions** with release dates.

---

## ✅ Step 4: Install a Specific Flutter Version

To install Flutter **3.29.1**, run:

```bash
fvm install 3.29.1
```

This process will:

* Download Flutter SDK
* Install Dart SDK
* Set up Flutter tools
* Resolve dependencies

After installation, verification output looks like:

```text
Flutter 3.29.1 • channel stable  
Dart 3.7.0 • DevTools 2.42.2
```

---

## ✅ Step 5: Verify Installed Versions

Run:

```bash
fvm list
```

Example output:

```text
Version: 3.29.1  
Channel: stable  
Flutter Version: 3.29.1  
Dart Version: 3.7.0  
```

---

## ✅ Step 6: Set Flutter Version for This Project

To link Flutter **3.29.1** with this project:

```bash
fvm use 3.29.1
```

You may receive this warning:

```text
Dart SDK 3.7.0 does not meet the project constraints of ^3.10.1.
```

You can safely proceed by typing:

```text
yes
```

After this, your project is locked to:

```text
✓ Project now uses Flutter SDK : 3.29.1
```

This creates a hidden **.fvm/** folder and updates project configuration.

---

## ✅ How to Use Flutter with FVM

From now on, always use:

```bash
fvm flutter run
fvm flutter pub get
fvm flutter build apk
```

Instead of:

```bash
flutter run
```

This guarantees that the correct Flutter version is used every time.

---

## ✅ Why We Use FVM

* Ensures **same Flutter version across all machines**
* Prevents **version conflicts**
* Improves **CI/CD stability**
* Easy **downgrade & upgrade**
* Supports **multiple projects with different versions**

---


