# riscv-starfall (mini-rv32ima-lua)

![Linux/RV32 inside Garry's Mod](.assets/linux.jpg)

# Summary
This is a port of [mini-rv32ima](https://github.com/cnlohr/mini-rv32ima) to Lua (specifically for [StarfallEx](https://github.com/thegrb93/StarfallEx)).

# How it works (briefly)
Starfall is pretty different from E2, in a way that client and server are separated. This means if one of the client CPU crashes, the server CPU continues to run and vice versa.

As for this port, the CPUs does the following:
- Server: handles keypresses from Wire Keyboard, and Wire Console Screen output
- Client/Owner: Load binary image from local storage, allocate it's own memory and handles RV32 logic

# Notes
Please keep in mind that:
- This implementation **is not comformant** and **not suitable for production use**.
- It is **VERY SLOW** with the quota limit, you can increase the timebuffer to make it faster or you can disable the quota limit (any demanding tasks will hang the game for a moment)
- **USE AT YOUR OWN RISK**

# Try
1. Put `rv32ima_emulator.txt` to `data/starfall`
2. Copy your [dtb](https://github.com/cnlohr/mini-rv32ima/blob/master/mini-rv32ima/sixtyfourmb.dtb) and [boot image](https://github.com/cnlohr/mini-rv32ima-images) to `data/sf_filedata`
3. Edit `rv32ima_emulator.txt` and point it to your boot files
4. Spawn the chip
5. Connect Wire Console Screen and Wire Keyboard to the chip
6. Restart the chip

# Screenshots
![](.assets/linux.jpg)
![](.assets/coremark.jpg)

# Thanks
- Originally this was an E2 port, and I've took some code from [riscv-vscript](https://github.com/misyltoad/riscv-vscript). But since Starfall has more functions, a lot of this has been reworked.
- Charles Lohr for [mini-rv32ima](https://github.com/cnlohr/mini-rv32ima)
