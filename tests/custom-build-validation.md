# Combined custom build validation

Validated on 2026-10-22, upstream 3.9.0 (9a6b209) plus the two feature
branches, on codex/tinta-custom-3.9.0. Neither PR branch is modified.

- Built tinta, input_tests, i18n_tests and russian_ui_tests in MSVC x64 Release.
- Python translation validation passed: 357 unique keys, full English key
  coverage, nonempty translations and matching printf arguments.
- Eleven CTest checks passed: deleted_tab, editor_features, input_shortcuts,
  file_fragment_navigation, tab_drop_position, tab_hover_card,
  search_results_panel, wrapped_cursor_navigation, ui_font_language,
  i18n and russian_interface.
- The deleted-tab native test explicitly selects Russian on this combined
  branch and verifies the translated retention label, then exercises the
  retained viewer/editor and real Save As dialog including cancellation.
- Russian settings rendered all four sections at widths 650 and 1050 in
  themes 0 and 5. Visually inspected General at 650/light and 1050/dark,
  including the retention switch and RAM hint.
- The built tinta.exe printed tests/fixtures/custom-build.md with isolated
  language=ru and keepDeletedTabs=1 settings. Exit 0, one PNG page, visually
  inspected heading, Cyrillic, table, numbered list, quote, link and code.
  Output: build/custom-build-check/fixture-pages/page-1.png.
- The known upstream scroll-sync CRLF limitation from
  deleted-tab-validation.md remains documented; that check was not rerun
  for this combined build. Windows system language was not changed.

Screenshots, executables and portable packages are ignored build/output artifacts.
The product version remains 3.9.0; the README and package identify this custom fork.
