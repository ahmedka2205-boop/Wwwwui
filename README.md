# WhatsApp Simulation (safe) - Local Research Environment

This repository contains a safe, local simulation environment for A/B experiments that model phishing-like flows (link → landing page → optional QR / form). It is intended for research and educational use on devices/accounts that you control. It does NOT contain or enable any real exploitation.

Contents:
- `server.py` — an integrated Flask-based local server that serves the simulation UI, accepts uploaded session JSON, and auto-processes to CSV summaries. Bind to `127.0.0.1` only.
- `index.html` — standalone client-only simulation UI you can open directly (or host via GitHub Pages for viewing). Generates synthetic session JSON.
- `requirements.txt` — Python dependencies for running `server.py`.
- `.gitignore` — ignores runtime folders.

Quick start (local):

1. Install Python 3.8+ and pip.
2. Install requirements:

   ```bash
   pip install -r requirements.txt
   ```

3. (Optional) set admin credentials (recommended):

   Linux/macOS:
   ```bash
   export SIM_ADMIN_USER=myuser
   export SIM_ADMIN_PASS=strongpassword
   ```

   Windows (PowerShell):
   ```powershell
   setx SIM_ADMIN_USER "myuser"
   setx SIM_ADMIN_PASS "strongpassword"
   ```

4. Run server (binds to localhost only):

   ```bash
   python server.py
   ```

5. Open http://127.0.0.1:5000 in your browser to access the integrated UI.

Using `index.html` directly:
- You can open `index.html` in a browser (File → Open) to view and run the client-side simulation. To upload results to the local server use the "Upload to Local Server" control and set server credentials.

Security & Ethics:
- Use only synthetic/test accounts and devices you control. Do NOT target real users.
- The server listens on `127.0.0.1` and uses Basic Auth for the upload/processed endpoints. DO NOT expose it to the public internet.
- Clean up `uploads/` and `processed/` after experiments.

If you want, I can also enable GitHub Pages for this repo (to serve `index.html`) by providing the exact Settings steps or automate a branch push. If you want me to replace the repository contents differently, tell me.