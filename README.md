# Darcy confidential desktop PoC

Separate from production Darcy web. Temporary CPU-only Linux desktop, no persistent disk, no production keys or files.

Measured releases pin the runtime image and owner access-key hash. Screenshots and input require an attested encrypted POST plus the separate PoC access key. No public VNC, direct SSH or debug mode. Chromium must retain its namespace and seccomp sandbox.
