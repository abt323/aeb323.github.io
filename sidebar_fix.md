🧭 Jupyter Book Sidebar + TOC Fix (Later Checklist)
1️⃣ Clean rebuild of the book

From your repo root:

jupyter-book build .


✅ Confirms _build/html/ exists and looks correct (open _build/html/index.html locally — you should see the sidebar there).

2️⃣ Publish to a gh-pages branch (the easiest way to restore theme + sidebar)
pip install ghp-import
ghp-import -n -p -f _build/html


Then, in GitHub:

Settings → Pages

Source: “Deploy from a branch”

Branch: gh-pages

Folder: / (root)

Save and wait ~60 seconds.
🔗 Your fully themed site (with sidebar + TOC) will be at
https://abt323.github.io/aeb323.github.io/

3️⃣ (Optional) Simplify publishing for future projects

Create a file named publish.sh in the repo:

#!/bin/bash
jupyter-book build .
ghp-import -n -p -f _build/html


Then make it executable:

chmod +x publish.sh


Now you can just run:

./publish.sh


each time you want to publish updates.

4️⃣ Optional visual polish

In _config.yml, you can later set:

html:
  use_repository_button: true
  use_edit_page_button: true
  use_issues_button: true
  baseurl: /aeb323.github.io/


and update your title: to "Alexander Bitterman’s Portfolio" for consistent branding.