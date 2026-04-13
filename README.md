# Installation

## Option A — Prism Launcher (recommended for most players)

1. Install [Prism Launcher](https://prismlauncher.org/download/)
2. Install [Temurin JRE 25](https://adoptium.net/en-GB/temurin/releases?version=25&package=jre) — pick your OS/arch
3. In Prism: `Settings → Java → Java Runtime` → point to your Temurin install
   - Recommended memory: **4–6 GB** (`-Xmx6G`)
   - Add these JVM flags for best performance:
     ```
     -XX:+UseZGC -XX:+UseCompactObjectHeaders
     ```
4. Download `pack.mrpack` from this repo and import it:
   **Prism → Add Instance → Import** → select the downloaded `pack.mrpack`
   
   > **Java version warning:** Prism may warn that Java 25 is incompatible. Ignore it — go to **Edit Instance → Settings → Java** and uncheck *Java compatibility check*. Java 25 works fine.

5. Hit **Play** — NeoForge installs automatically

## Option B — Packwiz (for mod developers / pack maintainers)

Packwiz lets Prism auto-update from this repo on every launch.

1. Install [Prism Launcher](https://prismlauncher.org/download/)
2. Prism → **Add Instance** → **Custom** → set MC version to `1.21.1` + NeoForge `21.1.226`
3. In the instance, go to **Edit** → **Mods** → install [packwiz-installer-bootstrap](https://github.com/packwiz/packwiz-installer-bootstrap/releases) as a pre-launch command:
   ```
   $INST_JAVA -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/GriffynHancock/GaurasAdventure/modpack/pack.toml
   ```
4. Mods auto-download and update on every launch

---

**MC Version:** 1.21.1 · **Modloader:** NeoForge 21.1.226 · **Mods:** ~197 client-side

---

## Rebuilding pack.mrpack (maintainers)

After adding/updating mods in `mods/`, regenerate the mrpack:

```bash
python3 /home/Minecraft/build_mrpack.py
```

Commit both the updated `mods/` tree and `pack.mrpack`.
