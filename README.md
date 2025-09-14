# Fix GNOME "Oh no! Something has gone wrong." after upgrading to Ubuntu 24.04

<div align="center">
  <img src="https://github.com/user-attachments/assets/c26b244e-66d8-4777-a6cb-a23033d9d572" alt="GNOME Error" />
</div>


After upgrading to **Ubuntu 24.04**, you might encounter an error screen that says:

> Oh no! Something has gone wrong.  
> A problem has occurred and the system can't recover. Please contact a system administrator.

This usually happens due to issues with the desktop session manager (`ubuntu-session`) or GNOME components.

## ✅ How to Fix

Follow these steps to fix the issue:
1. **Restart your computer.**
2. At the GRUB boot menu, select: `Advanced options for Ubuntu`
3. Choose the entry with: `(recovery mode)`
4. In the Recovery Menu, choose: `root - Drop to root shell prompt`
5. You will see a message like: `Press Enter for maintenance (or press Control-D to continue)`
6. Press **Enter** to access the root shell prompt.
7. Run the following commands to reset and reinstall the desktop environment:
   ```bash
    sudo apt purge ubuntu-session
    sudo apt install ubuntu-desktop
8. After the installation finishes, reboot your system: `reboot`

## 📌 Notes
- Ensure your internet connection is available when running the commands (Ethernet or enable networking from recovery menu).
- This fix applies to systems using the default GNOME desktop environment.

## 🔧 Tested On
- Ubuntu 24.04 LTS (Noble Numbat)

Issue occurred after a full system upgrade from 22.04 LTS
