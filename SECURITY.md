# Security policy

## Reporting a vulnerability

Use **Security → Report a vulnerability** on this repository. The report stays private
until there is a fix; please don't open a public issue for a security problem.

If that button isn't there, open an issue asking for contact — without the details.

## Supported version

The `main` branch only. There are no tagged releases — you import whatever is on
`main` at the time.

## What is worth reporting

This repository holds keyboard settings, layouts and a theme for Multiling O Keyboard.
There is nothing here that executes on your machine. What still matters:

- **personal data inside a settings dump.** `settings.mok.txt` is an
  `OK_Settings_Begin` export from the app, and that format can carry the user
  dictionary, clipboard entries and macros along with the layout. The files published
  here were checked and contain only layout definitions and the app's own default
  clipboard list — the single e-mail address in them, `OKeyboard.M@gmail.com`, is the
  app author's, not a user's. If you spot anything personal that slipped through,
  report it and it will be removed;
- a layout or macro definition that sends typed text somewhere, or that silently
  rebinds a key to something other than what its label shows.

## Out of scope

Vulnerabilities in Multiling O Keyboard itself — report those to the app author at
<http://honsoapps.appspot.com/1/1.html> or on
[r/MultilingOKeyboard](https://www.reddit.com/r/MultilingOKeyboard/).

## Before you publish your own dump

Export from **Settings → Misc. → Import | Export**, then read the file before pushing
it anywhere. Your dictionary and clipboard history travel inside it.
