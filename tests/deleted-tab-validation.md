# Deleted file tabs

The General setting "Keep deleted files in memory" is off by default and
warns "Increases RAM usage; until Tinta closes". Its choice persists in
settings.ini as keepDeletedTabs. Enabling snapshots already open files;
disabling immediately releases all per-tab viewer source copies.

When enabled, tabs retain their last readable source in memory only. A missing original
can still be selected and edited. Save (including Ctrl+S) opens Save As when
the original or its parent folder no longer exists. The old filename is
suggested, but a destination must be explicitly confirmed; cancellation
keeps the text, path and editor open. Existing disk files take precedence on tab activation. Empty files
have a valid empty snapshot. Closing a tab or exiting the process releases
its source copy. No persistent viewer cache is written or read. The existing
session restore continues to skip missing files on the next launch.
Existing unsaved editor draft recovery is unchanged.

Fixture: `tests/fixtures/deleted-tab.md`, a mixed document with Cyrillic,
headings, a table, lists, emphasis, a quote, a link and code.

## Verification

- Built `tinta` and `input_tests` with Visual Studio 2026, MSVC x64 Release.
- Seven CTest checks passed: `deleted_tab`, `editor_features`, `input_shortcuts`,
  `file_fragment_navigation`, `tab_drop_position`, `tab_hover_card`,
  `search_results_panel`.
- The native deleted-tab test covers deletion while active, switching,
  editing, discarding edits, parked editor recovery, saving to recreate the
  document through an explicitly confirmed Save As, externally recreated files, deleted empty files, inactive
  session-seeded tabs, failed opens, releasing cached state on close, and
  the absence of a recovery copy after all in-memory tabs are discarded.
- It verifies that no `tab-cache/` directory is created.
- Native settings mouse input verifies enabling, disabling, immediate
  memory release, persistence of both values, and disabled-file behavior.
- Settings previews were rendered through a GDI-compatible Direct2D target
  and visually inspected in light/dark themes at widths 650 and 1050.
  The switch and full RAM warning fit inside the panel. PNGs live at
  `build/deleted-tab-memory-test-Release/settings-THEME-WIDTH.png`.
- Cached content is laid out at widths 500 and 1000 with themes 0 and 5.
  The native print harness produces `build/deleted-tab-memory-test-Release/cached-pages/page-1.png`.

The native Save As dialog is now exercised with a thread-local CBT hook in
the test process: cancel, a new destination, explicit reuse of the old name,
save-and-exit cancellation, and a deleted parent folder. Normal saves of
existing edited files are checked to bypass the picker. A 30-second wrapper
timeout bounds dialog failures. No production dialog hooks were added.
The fixture read normalizes CRLF to match the viewer's text-mode input.
Files already deleted before this version first read them cannot be recovered.

## Integration with upstream 3.9.0

Merged upstream master 9a6b209 on 2026-10-21. The only textual conflict was
in the input_tests source list; both deleted_tab_tests.cpp and the upstream
scroll_sync_tests.cpp are retained.

Built tinta and input_tests in x64 Release. Nine checks passed with the
normal Windows checkout: the seven checks above, ui_font_language and
wrapped_cursor_navigation. The additional upstream edit_preview_scroll_sync
check failed two heading-position assertions with the CRLF fixture (22 lines
off); it passed with that same fixture temporarily normalized to LF. The
original fixture bytes were restored after the check. No upstream test or
fixture was permanently changed to mask this limitation.

## Closing beside unavailable tabs (#275)

A native regression added on 2026-10-22 reproduced the invalid active index
and wrong document identity before the fix (seven failed assertions; no
full-app crash was claimed). It creates real native App instances, opens
copies of the mixed Markdown fixture, removes inactive files and closes the
active tab with retention disabled (the default).

The four cases cover a missing left neighbor, a missing right neighbor,
an available third tab beyond a missing neighbor, and multiple missing
survivors. Closing now tries available neighbors before removing the active
tab; if none can activate, its slot becomes a start page while missing tabs
remain available for explicit closure or later recreation. Dirty-close
confirmation also requires the requested tab to be active.

After the fix, tinta and input_tests built in MSVC x64 Release and all nine
checks listed under integration passed, including deleted_tab. Existing
active/inactive retention, recovery Save As and settings checks still run.
