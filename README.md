# Material GNOME

A modern, cohesive theme for the GNOME desktop environment inspired by Google's Material You and Material 3 design languages. It provides a unified visual experience across GTK3, GTK4, and GNOME Shell with a focus on deep container colors, expressive active states, and minimal visual clutter.

![Showcase](https://raw.githubusercontent.com/username/Material-Gnome/main/preview.png)

---

## 📂 Repository Structure

```text
Material-Gnome/
├── gtk-3.0/         # GTK3 Stylesheet & Assets
├── gtk-4.0/         # GTK4 & Libadwaita Stylesheet
├── gnome-shell/     # GNOME Shell Desktop Theme
└── index.theme      # Desktop Theme Metadata
```

---

## ✨ Features

* **True System-Wide Consistency:** Unified styling across legacy GTK3 apps, modern GTK4/Libadwaita apps, and the GNOME Shell interface.
* **Material 3 Container Architecture:** Styled with container shapes, adaptive active states, and expressive focus indicators (like the segmented view-switcher design).
* **Self-Contained Color System:** Colors are declared natively per toolkit—making the theme independent, lightweight, and incredibly easy to modify without external dependencies.
* **Dynamic-Ready (Optional):** Completely compatible with color-generation backends like `matugen` or `gradience`.
* **Dark-First Design:** Optimized specifically for modern dark-mode workflows to minimize eye strain.

---

## 🚀 Installation

### 1. Deploy the Theme Files

Clone or extract the theme directory to your local or system themes folder:

**Local User Deployment (Recommended):**

```bash
mkdir -p ~/.themes
cp -r Material-Gnome ~/.themes/
```

**System-Wide Deployment:**

```bash
sudo cp -r Material-Gnome /usr/share/themes/
```

### 2. Enable GNOME Shell Theme Support

GNOME Shell requires the **User Themes** extension to load custom desktop stylesheets.

* **Fedora/RHEL:** `sudo dnf install gnome-tweaks gnome-extensions-app gnome-shell-extension-user-theme`
* **Ubuntu/Debian:** `sudo apt install gnome-tweaks gnome-shell-extension-manager gnome-shell-extension-user-theme`
* **Arch Linux:** `sudo pacman -S gnome-tweaks gnome-shell-extensions`

> 💡 **Note:** Open your system **Extensions** application and ensure the **User Themes** extension is toggled **ON**.

### 3. Apply the Theme

#### GTK3 & GNOME Shell

Open **GNOME Tweaks** and navigate to the **Appearance** tab:

* Set **Legacy Applications** (or Applications) to `Material GNOME`.
* Set **Shell** to `Material GNOME`.

#### GTK4 / Libadwaita Applications

Modern Libadwaita apps look into your local user configuration instead of `~/.themes`. To force GTK4 apps to follow your theme, symlink the files into your local configuration directory:

```bash
mkdir -p ~/.config/gtk-4.0
ln -sf ~/.themes/Material-Gnome/gtk-4.0/gtk.css ~/.config/gtk-4.0/gtk.css
ln -sf ~/.themes/Material-Gnome/gtk-4.0/gtk-dark.css ~/.config/gtk-4.0/gtk-dark.css
```

---

## 📦 Flatpak Application Support

Flatpak applications run in isolated sandboxes and cannot access your local theme directories by default. To make them follow your theme, run the following commands:

1. **Grant filesystem permission:**

```bash
flatpak override --user --filesystem=$HOME/.themes:ro
```

2. **Force the theme environment variable:**

```bash
flatpak override --user --env=GTK_THEME=Material-Gnome
```

---

## 🛠️ Configuration & Tweaks

If you want to tweak or override specific elements (like changing the accent colors), you can modify the primary palette definitions found at the top of the respective stylesheets:

* **GTK3:** `gtk-3.0/colors.css`
* **GTK4/Libadwaita:** `gtk-4.0/colors.css`
* **GNOME Shell:** `gnome-shell/gnome-shell-template.css`

---

## 📜 License

This project is licensed under the **GPL-3.0 License** - see the [LICENSE](LICENSE) file for details.
