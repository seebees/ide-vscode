# Release Notes

## 2.8.1
- Use Dafny [v3.8.1](https://github.com/dafny-lang/dafny/releases/tag/v3.8.1) which contains critical language server fixes
- Fix disappearing resolution errors with verification tests. (https://github.com/dafny-lang/ide-vscode/pull/260)

## 2.8.0
- Update Dafny and language server to [v3.8.0](https://github.com/dafny-lang/dafny/releases/tag/v3.8.0)
- Feat: Enable displaying verification as tests when using the latest Dafny version
- Fix a bug in Windows where the gutter's skipped lines are wrong. (https://github.com/dafny-lang/ide-vscode/pull/255)
- Previously, in Windows, the LSP's string URI were a bit different than the VSCode's Uri.toString().
- Namely, the LSP was retuning:
- `file:///c:/...`
- whereas `Uri.ToString()` in VSCode was returning
- `file:///c%3A/...`
- Thus, this PR transforms URI received by the LSP into their canonical form for the Verification Symbol Status view, where the canonical URI is needed because of the event handler `e.document.uri.toString()` in `window.onDidChangeTextDocument`
- Second, this PR stores the latest nightly build version so that if the GitHub API rate limit is reached, a client will not revert to the previous stable version.
- Third, deactivated two problematic tests that are passing locally but timeout in CI because of seemingly restrictive API quota limits.
- Do not show status updates for non-active documents (https://github.com/dafny-lang/ide-vscode/pull/254)
- * Do not show status updates for non-active documents
- * Remove unused import
- Do not show verified status message when no solvers are free (https://github.com/dafny-lang/ide-vscode/pull/253)
- Prevent overlap of play and gutter icons on parent nodes (https://github.com/dafny-lang/ide-vscode/pull/252)
- * Prevent overlap of play and gutter icons on parent nodes such as classes and modules
- * Prevent visible and internal state of testItems from getting out of sync
- * Add debug information
- Correctly handle a difference between verifiable and document symbols (https://github.com/dafny-lang/ide-vscode/pull/249)
- Adding brew update as part of the manual source installation (https://github.com/dafny-lang/ide-vscode/pull/250)
- Ensure gutter icons show up in the correct locations (https://github.com/dafny-lang/ide-vscode/pull/241)

## 2.7.0
- New: Add verification management UI (https://github.com/dafny-lang/ide-vscode/pull/229)
- Syntax highlighting after "var" fixed (https://github.com/dafny-lang/ide-vscode/pull/231)
- Release script (https://github.com/dafny-lang/ide-vscode/pull/228)
- Fix the restart server command (https://github.com/dafny-lang/ide-vscode/pull/232)

## 2.6.3
- Set a default time limit of 20 seconds to avoid long freezes (https://github.com/dafny-lang/ide-vscode/pull/225)
- Fixed typo (https://github.com/dafny-lang/ide-vscode/pull/216)
- Added variable declaration to avoid mixing a function call with a type declaration. (https://github.com/dafny-lang/ide-vscode/pull/222)
- Fixed the CI (https://github.com/dafny-lang/ide-vscode/pull/223)

## 2.6.2
- Update Dafny and language server to [v3.7.3](https://github.com/dafny-lang/dafny/releases/tag/v3.7.3)

## 2.6.1
- Fixed the compiler command line (https://github.com/dafny-lang/ide-vscode/pull/205)

## 2.6.0
- Update Dafny and language server to [v3.7.2](https://github.com/dafny-lang/dafny/releases/tag/v3.7.2)
- Feat: Use nightly releases (https://github.com/dafny-lang/ide-vscode/pull/196)
- Feat: Hide either "Show Counterexample" or "Hide Counterexample" from the menu, depending on the state (https://github.com/dafny-lang/ide-vscode/pull/191)
- Fix: Multiline strings correctly highlighted (https://github.com/dafny-lang/ide-vscode/pull/202)
- Fix: Highlighting of nested types (https://github.com/dafny-lang/ide-vscode/pull/199)
- Fix: Missing images for the gutter (https://github.com/dafny-lang/ide-vscode/pull/200)
- Fix: Better dotnet and brew install errors for Mac M1 (https://github.com/dafny-lang/ide-vscode/pull/186)
- Fix: Better installation and java recognition for Mac M1 (https://github.com/dafny-lang/ide-vscode/pull/183)

## 2.5.0

- Update Dafny and language server to [v3.7.0](https://github.com/dafny-lang/dafny/releases/tag/v3.7.0)
- Underline related errors in postconditions (https://github.com/dafny-lang/ide-vscode/pull/164)
- Show verification status in the gutter (https://github.com/dafny-lang/ide-vscode/pull/147)
- Make status bar clickable and open a Dafny command menu (https://github.com/dafny-lang/ide-vscode/pull/125)
- Improved error messages
- Various fixes

## 2.4.0

- Update Dafny and language server to [v3.6.0](https://github.com/dafny-lang/dafny/releases/tag/v3.6.0)
- Fix issue related to Dafny installation on OSX M1 architectures
- Fix not sending obsolete notification to user
- Fix: Nested comments now displayed correctly

## 2.3.0

- Update Dafny and language server to [v3.5.0](https://github.com/dafny-lang/dafny/releases/tag/v3.5.0)
- Fix bug causing the red error squiggles to disappear
- Improved syntax highlighting

## 2.2.0

- Add option to specify the preferred dafny version for automatic installation
- Treat empty compiler/language server paths as unconfigured (use automatic installation)
- Accept .NET 6.0 as a supported platform
- Show verification progress messages (if available)
- Add option to configure Dafny's caching policy
- Fix the text selection for highlighted ghost statements
- Several improvements to the syntax highlighting

## 2.1.1

- Changed the marketplace publisher to dafny-lang
- Now marking ghost statements by default (requires Dafny 3.4.0+)
- Fixed issue when compiling untitled documents
- Changed 'Compilation Succeeded' status message to 'Resolved (not verified)'

## 2.0.2

- Improved syntax highlighting of strings

## 2.0.1

- Fixed VSCode compatibility (Promise.any is not a function error)

## 2.0.0

- Revised the code base
- Setting a custom Dafny installation now disables automatic updates
- Now showing the Dafny installation progress in the terminal
- Improved syntax highlighting
- Added option to set a time limit for the automatic verification
- Added option to set the number of virtual cores to use for automatic verification
- Updated Dafny and language server to [v3.3.0](https://github.com/dafny-lang/dafny/releases/tag/v3.3.0)

## 1.8.0

- Group verification errors and their related locations by using the "Related Information" UI for diagnostics.
  
## 1.7.0

- Now showing parser and resolver errors in the status bar.

## 1.6.0

- Updated Dafny and language server to [v3.2.0](https://github.com/dafny-lang/dafny/releases/tag/v3.2.0)
- Updated keywords

## 1.5.0

- Made the terminal command prefix configurable.
- Added verification activity indicator to the status bar.
- Updated Dafny and language server to [v3.1.0](https://github.com/dafny-lang/dafny/releases/tag/v3.1.0)

## 1.4.0

- Updated the required .NET runtime to ASP.NET Core 5.0.
- Updated the language server to [v3.0.0](https://github.com/dafny-lang/language-server-csharp/releases/tag/v3.0.0).
- Added configuration for the automatic verification.

## 1.3.0

- Dropped the Preview notes

## 1.2.0

- Updated the language server to [v2.3.0](https://github.com/dafny-lang/language-server-csharp/releases/tag/v2.3.0) ([Dafny 3.0.0 PreRelease2](https://github.com/dafny-lang/dafny/releases/tag/v3.0.0-PreRelease2)).
- Removed the server starting/started notification messages.

## 1.1.1

- Fixed the compile command invocation for ubuntu and osx installations.

## 1.1.0

- Re-added the possibility to show counter examples.
- Re-added the compiler related commands.
- Updated the language server to [v2.2.0](https://github.com/dafny-lang/language-server-csharp/releases/tag/v2.2.0).

## 1.0.7

- Replaced the language server runtime with .NET Core.
- Added automatic installation of the language server for OSX and Linux.
- Updated the language server.

## 1.0.6

- Replaced the backing Dafny language server
- Added configuration options to specify the launch arguments of the language server

## 1.0.6

- Replaced the backing Dafny language server
- Added configuration options to specify the launch arguments of the language server

## 1.0.5

- Addes support for the Dafny language server version 1.2.3

## 1.0.4

- Code refactorings and README updated.

## 1.0.3

- The Dafny language server is automatically downloaded from the client.

## 1.0.2

- Clean up Release Information

## 1.0.1

- Test-Release for CI

## 1.0.0

- Use new Language Server integrated with Dafny

## 0.17.2

- Improve highlighting for current dafny version ([#56](https://github.com/DafnyVSCode/Dafny-VSCode/pull/56))
- Upgrade `https-proxy-agent` and `lodash` to fix security vulnerabilies

## 0.17.1

- Correct Dafny Github repository name ([#49](https://github.com/DafnyVSCode/Dafny-VSCode/issues/49))
- Change typescript target from es6 to es2017
- Upgrade `js-yaml` to 3.13.1 to fix security vunerability
- Upgrade Dafny in tests to 2.3.0

## 0.17.0

- Rename configuration option `monoPath` to `monoExecutable` ([#40](https://github.com/DafnyVSCode/Dafny-VSCode/pull/40))
- Update deprecated API calls ([#39](https://github.com/DafnyVSCode/Dafny-VSCode/pull/39))
- Remove deprecated Flow Graph Visualization
- Update minimal VSCode version to 1.25.1
- Update dependencies
- Extension code clean up

## 0.16.0

- Allow customizing the arguments passed to the verify backend ([#42](https://github.com/DafnyVSCode/Dafny-VSCode/pull/42)).
- Update insecure dependencies

## 0.15.0

- Change extension key from FunctionalCorrectness to correctnessLab.
- Fix tslint errors ([#38](https://github.com/DafnyVSCode/Dafny-VSCode/pull/38)).

## 0.14.3

- Rebranding and small readme fixes.

## 0.14.2

- Add workaround for dafny counterExample bug ([#23](https://github.com/DafnyVSCode/Dafny-VSCode/issues/23)).

## 0.14.1

- Clearify mono installation message on macOS.
- Fix incomplete copyright notice and improve contributors section in readme ([#37](https://github.com/DafnyVSCode/Dafny-VSCode/issues/37)).

## 0.14.0

- Fix installation of Dafny on some constellations on Windows ([#7](https://github.com/DafnyVSCode/Dafny-VSCode/issues/7)).
- Check for a recent mono version on launch.

## 0.13.0

- Fixed the CodeLens references counter (Thanks [@GoryMoon](https://github.com/GoryMoon)!)
- Dependencies were upgraded to prevent several vulnerabilities.

## 0.12.0

- The Dafny base path can now alternatively be set via the environment variable DAFNY_PATH.
- Dependencies were upgraded to prevent several vulnerabilities.

## 0.11.1

Use Dafny releases from Microsoft/dafny. Miscellaneous bug fixes.

## 0.10.10

BugFix: Decrease guard

## 0.10.9

BugFix: Rename method

## 0.10.8

Warning if no workspace is used
Changelog

## 0.10.7

BugFix Ubuntu

## 0.10.2

Added Context Menu Commands

## 0.10.1

Manually show counterexample, flow graph

## 0.10.0

Display counter example for failing proof. Switched to typescript implementation to download dependencies. Lots of bugfixes

## 0.9.0

Switched to Language Server. IntelliSense for classes, compile and execute Dafny program in VSCode. QuickFix for decrease, increase and object may be null.

## 0.8.0

CodeLens showing method references, Go to Definition, version checking for newer Dafny release.

## 0.6.0

DafnyDef allows to get SymbolInformation from DafnyServer, which will allow in the future to implement Refactorings. Go to Definition is already implemented.

## 0.5.5

Fallback to wget, if curl is not found.

## 0.5.4

Automatic validation as you type.

## 0.5.1

Smaller bugfixes.

## 0.5.0

Automatic download and installation task on osx and ubuntu `dafny.installDafny`. Also added uninstaller `dafny.uninstallDafny`.

## 0.4.4

Uninstall task of dafny on windows.

## 0.4.0

Automatic download and installation task on windows.

## 0.2.0

Full refactoring of the plugin. issues/3 from ferry~ fixed.

## 0.1.2

Refactored/tweaked UI code, Added `dafny.restartDafnyServer` ("Restart Dafny Server") command.

## 0.1.0

Added syntax highlighting, tested on Ubuntu and OSX.

## 0.0.3

Getting `mono` from PATH when `monoPath` isn't set.

## 0.0.2

Fixed readme and license, added use animation.

## 0.0.1

Initial release, some half baked features turned off.
