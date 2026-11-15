# Google Drive delivery

Select the delivery set under [delivery-formats.md](delivery-formats.md). Image-only requests save only their requested PNG/SVG files; their HTML authoring source and validation captures remain private/local unless separately requested. Other visual requests retain the authored HTML and inspected preview route. Preserve source editability locally and deliver the exact requested formats; do not redraw merely to add a format. Chat-only replies, private checks and skill source edits do not require Drive uploads.

The destination is the Drive account and folder the user chose. Recheck the connected account and folder metadata before writing; connector identifiers may change. Do not silently use another account or folder, or change sharing.

1. Save and inspect the local originals. Preserve old outputs; use a distinct filename/version for a new result.
2. Upload only the selected deliverable files to the verified folder. Do not upload hidden HTML sources or extra preview files for an image-only request.
3. Fetch metadata separately: file ID, name, MIME, size, folder parent and actual web link.
4. Fetch the stored raw file and compare its bytes/hash with the local original. An upload acknowledgement alone is not verification. Do not expose signed download URLs or credentials.
5. Return observed Drive links. If upload/readback is blocked, retain local files and disclose exactly which storage check remains incomplete.
