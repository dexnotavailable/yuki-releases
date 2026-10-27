# yuki-releases

The public shelf for **YUKI**, a local AI agent for your own PC. Three things live here:

- **Installers.** Each [release](../../releases) carries the Windows installer (`YUKI-Setup-<version>.exe`).
- **Update manifests.** `latest.yml` and the installer's `.blockmap` sit on each release. The app reads them to
  update itself in small pieces and then asks you to restart. Betas are marked as pre-releases; only apps set to the
  beta channel take them.
- **The catalogue.** [`catalogue/catalogue.json`](catalogue/catalogue.json) lists the models, skills and voices YUKI
  can download for you, checked against [`catalogue/catalogue.schema.json`](catalogue/catalogue.schema.json).
- **Yuki's voice.** The reference clips her bigger voice learns from (`voices/hina-1.0.0.zip`, ten short WAV clips,
  no model) and [`voices/hina.md`](voices/hina.md), which says where the voice comes from.

## No weights here, ever

The catalogue is a list of pointers: a Hugging Face repo, a file, a pinned revision, its SHA-256, its size, what YUKI
uses it for and roughly what graphics card it wants. Models download straight from their authors' Hugging Face repos
onto your PC, and YUKI checks every byte against the SHA-256 before it uses a file. Nothing in this repo is a model,
and nothing ever will be, including our own conversions.

Each entry carries a short licence summary and a link to the full licence. YUKI shows both before a download starts,
and you accept it there. Gated models only download through your own Hugging Face login.

## Taking something down

If you made something that is listed here and want it gone, [open an issue](../../issues/new) and it comes out of the
catalogue. No app update is needed: every YUKI that is online picks up the change within a few hours (six at most),
then stops offering the item and will not start a download of it.

## Installing

Download the newest `YUKI-Setup-<version>.exe` from [Releases](../../releases/latest). The installer is not code-signed
yet, so Windows SmartScreen may stop it the first time: choose **More info**, then **Run anyway**.
