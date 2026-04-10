# Designdoll on Linux

Working setup guide for running DesignDoll 6.1.0.1 on Linux using Bottles.

All versions are the latest available at the time of writing.

1. Create a new bottle:
   - select `custom`
   - architecture: `64 bit`
   - runner: `caffe`
     - may need to be installed in Bottles settings
     - works on `caffe-9.7`, `soda-9.0-1` didn't work
2. Install dependencies:
   - `dotnet48`
   - `d3dx9`
3. Go to settings and enable `DXVK` (tested on `dxvk-2.7.1`)
4. Modify the registry:
   - open registry editor in the bottle
   - navigate to `HKEY_CURRENT_USER/Software/Microsoft`
   - create a new key `Avalon.Graphics`
   - add new DWORD value named `DisableHWAcceleration` and set it to `1`
   - this prevents menus and modals from being black
5. Install DesignDoll
   - there might be some errors when installing XNA, just ignore them
6. Launch DesignDoll

What works:

- everything (?) - I spent very little time playing with it
- wayland
- performance is good

Known issues:

- browsing directories outside of wine's C drive can crash the app, so better save your projects inside the drive C
- there's an error when closing the app but it seems harmless

---

Thanks to <https://github.com/cromachina/docs/blob/main/design-doll-in-linux.md> for giving me the hope ❤️
