# Darcy confidential desktop PoC

Separate from production Darcy web. Temporary CPU-only Linux desktop, no persistent disk, no production keys or files.

Measured releases pin the runtime image and owner access-key hash. Screenshots and input require an attested encrypted POST plus the separate PoC access key. No public VNC, direct SSH or debug mode. Chromium must retain its namespace and seccomp sandbox.

Chromium requires a measured CVM-admin bootstrap here because the default CVM disables unprivileged user namespaces. The bootstrap runs single-threaded, enables user namespaces, irreversibly drops to UID/GID1000 with empty groups/capabilities and no-new-privileges, verifies the drop, then starts the API and desktop. The browser must add its own namespace and seccomp restrictions; no unsandboxed fallback. This exception is confined to the disposable PoC VM.
