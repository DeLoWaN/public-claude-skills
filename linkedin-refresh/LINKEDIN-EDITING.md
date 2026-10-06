# Editing LinkedIn in the browser

Facts about the LinkedIn editor, learned from real runs. Button labels follow the user's interface language; the French label is in brackets.

## Guardrails

- The network notification switch ("Informer le réseau") sits at the top of each position form. Keep it off unless the user asks for it, and check it on every form before you save.
- After a save, LinkedIn may offer to post the news, to connect with colleagues, or to try Premium. Click "Skip" ("Ignorer") or close the dialog every time.
- Leave every "Delete" ("Supprimer") button alone.

## Opening a form

- Direct edit URLs often redirect to the profile. Open the details page (`/in/<id>/details/experience/` or `/details/education/`) and click the pencil of the entry.
- A click on a link reference can do nothing. Then click the pencil by its coordinates from a fresh screenshot.
- Sections load lazily: scroll down, then wait before you search for an element.

## Filling text

- A form uses one of two field types: a rich editor (a `contenteditable` DIV) or a plain `textarea`. Form-filling tools work on the `textarea` only.
- Rich editor: click it, select all, delete, then type one paragraph per action. A blank line needs two line breaks.
- `textarea`: set the full value in one action. Typing into it can drop characters.
- A paste from the clipboard removes blank lines.
- After filling a field, read its counter (for example "1 985/2 000") and compare it with the count from your script. On a mismatch, clear the field and fill it again.

## Second language

- The second-language profile holds the name, the headline, the About text, and for each position its title and description. Each of these forms has one tab per language.
- Skills, dates, locations and education are shared by both languages.
- Save the primary tab first. Reopen the form for the other tab, so no unsaved change is lost.
- After a save in the second language, your own profile can show that language everywhere. Check with `?locale=fr_FR` and `?locale=en_US` on the profile URL before you conclude that a text was overwritten.

## Skills

- The 5 top skills live in the About form, under "Skills" ("Compétences").
- A position form has an "Add skill" button with autocomplete. The first suggestion can be wrong: "Windows Server" can give "Windows Server Update Services". Read the options and click the exact one.
- Click a ticked skill to untick it.
- Top skills cannot be reordered by drag and drop through automation. Tell the user to reorder them by hand.
- LinkedIn renames some skills, for example AWX becomes "Projet AWX". Report the names it used.

## Other sections

- A "Connected apps" card with greyed apps is a suggestion that only the owner sees. It holds nothing to remove; close it if the user wants it gone.
- Saving an education entry can show "Education added" ("Formation ajoutée") even for an edit. Check the list afterwards for duplicates.
