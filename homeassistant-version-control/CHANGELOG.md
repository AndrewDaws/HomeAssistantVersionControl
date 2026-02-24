# Changelog

## [1.2.0-beta.2]

### Added
- **Smart SSH Key Loader:** Persistently load SSH keys from `/config/.ssh` into the addon environment.
- **Trusted CA Certificates:** Automatically sync and trust root CA certificates from `/config/additional_ca` for secure connections to private Git remotes.
- **Max Commits Setting:** Added UI to configure the maximum number of commits retained in history.
- **Resizable Panels:** The side and main panels can now be resized by dragging the gap between them.
- **Header Palette Cycle:** Clicking the header title or logo now cycles through available accent color palettes.
- **Configurable Storage Tracking:** Added `include_storage` option to explicitly whitelist and version control specific files/patterns in the `.storage` directory (e.g., helpers, entities).
- **Remote URL Configuration:** Added `remote_url` option to the addon configuration to allow easily changing the remote repository URL from the Home Assistant UI.

### Fixed
- **Dynamic File Formats:** Fixed issue where `.py`, `.json`, and `.txt` formats were hardcoded to `false` in `server.js`, ignoring the `include_extensions` configuration.
- **Default Branch Transition:** New repositories now default to `main` (standard Git naming). Existing repositories on `master` or other branches are detected automatically and supported without intervention.
- **Cloud Sync Branch:** Improved dynamic detection to ensure sync always follows the active local branch.
- **UI Refinement:** Re-ordered settings menu for better logical flow (Max Commits moved below history retention).
- **Documentation:** Fixed Docker image name typo in README.

## [1.2.0-beta.1]
- Initial beta release with internal refactoring.

## [1.1.1]

### Fixed
- Fixed issue with `secrets.yaml` exclusion in cloud sync

## [1.1.0]

### Added
- **Cloud Backup:** Push your configuration to a private GitHub or Gitea repository. Choose to sync manually, daily, or automatically after every change.
- **Track More than Just YAML:** Now you can select any file format to track and backup! Configure extensions like .sh, .py, .json directly in the add-on's Configuration tab.
- **Recover Deleted Items:** View and restore files, automations, and scripts that have been deleted. Look for the "Deleted" option in the sort menu.
- **Progressive History Loading:** Versions now load faster, displaying results as they're found.
- **Quick Style Toggle:** Tap the header bar of any file diff to cycle through different visual themes instantly.
