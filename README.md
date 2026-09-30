# WALKABOUT

Four free tools for editing photo-walk and street-photography videos in DaVinci Resolve and Adobe Premiere Pro.

[Website and demonstrations](https://smallweblab.com/walkabout/) · [Download v0.2.0](https://github.com/RamonLinares/walkabout/releases/tag/v0.2.0) · [Report a problem](https://github.com/RamonLinares/walkabout/issues)

## Tools

- **Face Privacy** — detects and blurs faces, with manual corrections and optional people exclusions. Check coverage before publishing: detection can miss faces.
- **Photo Presentation** — frames photos and adds editable camera and exposure captions from EXIF metadata.
- **Arrange Photos** — spaces selected timeline photos by capture-time gaps. Align the result with your footage yourself.
- **Contact Sheet / Best of the Walk** — creates a photo grid with featured-photo animation.

## Download and install

Requires an **Apple Silicon Mac running macOS 13 or later**. Intel Mac and Windows are not supported in this release.

| Editor | Requirement | Installer |
|---|---|---|
| DaVinci Resolve | Studio 21.1 or later | [WALKABOUT for DaVinci Resolve 0.2.0](https://github.com/RamonLinares/walkabout/releases/download/v0.2.0/WALKABOUT-for-DaVinci-Resolve-0.2.0.pkg) |
| Adobe Premiere Pro | Premiere Pro 2026; tested with 26.5.1 | [WALKABOUT for Premiere Pro 0.2.0](https://github.com/RamonLinares/walkabout/releases/download/v0.2.0/WALKABOUT-for-Premiere-Pro-0.2.0.pkg) |

Save your work and quit the editor, open its installer, then reopen the editor. You can install both packages. Each package installs all four tools and the required models, helpers, guides and third-party notices. The effects install for all users; administrator authorization may be required. The packages are not Developer ID signed or notarized; their native binaries are ad-hoc signed.

**Resolve:** effects appear under **Open FX → WALKABOUT**. Arrange Photos appears under **Workspace → Scripts → WALKABOUT**, sometimes inside Utility. The free edition of Resolve has not been tested.

**Premiere:** effects appear under **Effects → Video Effects → WALKABOUT**. Run Arrange Photos from **Window → UXP Plugins → WALKABOUT**. The installer registers it for the logged-in user. If missing, double-click `/Library/Application Support/WALKABOUT/Premiere/WALKABOUT-ArrangePhotos.ccx`; other Mac accounts need to register that CCX themselves.

## Arrange Photos

Select photos in the timeline and run the command. Photos with capture metadata are spaced relative to the earliest capture and its current timeline position. Align the group with your video manually. Photos without usable metadata or from a different camera may be skipped.

In Resolve, arrange before adding effects, grades and keyframes: it creates an arranged copy and does not transfer all styling. In Premiere, the command clones the selected photos onto new tracks, preserving their attached effects, then removes the originals in one Undo transaction. Video is left in place. Use **Edit → Undo** to restore the original arrangement.

For Premiere Photo Presentation, use **Fit** when a source photo is larger than the sequence.

## Release checks and limits

On September 30, 2026, both v0.2.0 installers completed successfully on an Apple Silicon Mac. In Premiere 26.5.1, the installed Arrange Photos command arranged three selected photos in the isolated validation project; one Undo restored their original positions and the original 16-second timeline. All seven planner tests passed.

The native effects have earlier live checks for face analysis/manual corrections, photo captions and contact sheets. Broader playback/export profiling, full control parity, HDR/log/ACES, RAW, retiming and non-square pixels remain unvalidated. This test is a release smoke check, not a guarantee for every project or workflow.

Face processing and people libraries stay local. Review privacy coverage yourself. Keep linked gallery photos and people libraries available when moving projects.

## License and support

WALKABOUT is freeware: free for personal and commercial use. You may redistribute unmodified installers with the accompanying notices. See [LICENSE](LICENSE). This repository provides downloads and documentation; the development source is not published here. Third-party components retain their own licenses, included in the installers.

Provided as is, without warranty. For bugs, include your macOS version, editor/version, reproduction steps and any error text in a [GitHub issue](https://github.com/RamonLinares/walkabout/issues). Do not attach private footage or people libraries.
