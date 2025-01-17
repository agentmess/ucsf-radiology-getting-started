---
subtitle: "Matlab Tool Resources"
tags: [matlab]
---

## Matlab Resources

The servers have many versions of Matlab. Using Matlab is quite simple, all it requires is typing the following command into a terminal in a VNC server:

- `matlab &`
- The default matlab is usually R2015b, although this could change. In order to use a specific version, specify which version you would like to run:
  - e.g. `matlab_2013a &`
- To check all versions of matlab available in the server, run the following command in a terminal:
  - `bash -c "compgen -c | grep -E '^matlab.*[ab]' | sort"`

---

### Useful 3D visualization app in Matlab

[Imagine] is an useful visualization tool for 3D images, to download it, use the following command:

- `git clone https://github.com/imagineStudios/Imagine-Legacy.git ~/`

From the matlab command window, use the following commands:

- `addpath ~/imagine`
- `figure; imagine2(3D_data)`
  - Replace `3D_data` with your actual 3D data array

---

### Keyboard Mapping

There are several keybindings available for Matlab, with Emacs being the default for the radiology servers. If you are more comfortable with a Windows keybinding scheme (Ctrl+C to copy, Ctrl+V to paste, Ctrl+R to comment, etc) then you can change it by:

- Go to File or Environment > Preferences > Keyboard > Shortcuts
  - Change the Active Settings to *Windows*

---

<!-- Links -->
[imagine]: https://github.com/imagineStudios/Imagine-Legacy