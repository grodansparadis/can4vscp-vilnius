# Changes in can4vscp-vilnius

Every change that goes into a release is listed here, newest release first.
Add each change under **Unreleased** when it is made. When a release is
tagged, rename **Unreleased** to the version and date, and start a new
**Unreleased** section above it.

## Unreleased

- Updated license to CERN (0d5865e)
- Fixed cover page (6f6c2e4)
- Cleanup (df59896)
- Moved documentation to Markdown (f230ff4)
- Added missing nojekyll (33f3fbd)
- Added new manual skeleton (49988a2)
- Updated readme to have the same info as other can4vscp modules (2880076)
- Changed license to MIT (9354a7c)
- Adopted files to new naming convention (3e9c1df)
- Converted schemas to KiCad (3d3fa06)
- DM on page 3 in header is wrong, should be 2 (30add5f)
- Updated MDF version (55cc534)
- DM matrix pointer to register page 3 should be 2 (d887372)
- Fixed errors in mdf (e7663e6)
- Updated firmware (477fe52)

## v1.04 - 2020-05-15

- init timeout set to 2500 ms (5ff7da9)
- Updated paths for firmware, picture and manual (5703bc8)
- Added new link to bit timing (f32ff54)
- RA4 set to input to prevent collision with VCAP circuits in PIC18F2580. Brown out raised to maximum (3V & 4.6V). Valuable input from Anders Forsgren, AJE Electronics AB. (2f73abb)
- Changed value of C14 to 10uF (e929abc)
- Delete Vilnius.X.production.hex (ed0b368)
