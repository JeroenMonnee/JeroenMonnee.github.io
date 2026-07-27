# Start here: publishing the website

This folder is a complete Quarto website prepared for:

- Repository: `JeroenMonnee/JeroenMonnee.github.io`
- Public address: `https://jeroenmonnee.github.io`
- Automatic publishing: GitHub Actions

You do **not** need to understand Jekyll, Ruby, HTML templates, or the old Academic
Pages structure.

## Recommended installation route: GitHub Desktop

This is the safest route because your GitHub repository already contains the old website.

### 1. Make a backup of the current repository

On GitHub, open:

`https://github.com/JeroenMonnee/JeroenMonnee.github.io`

Choose **Code → Download ZIP** and save it somewhere as a backup.

### 2. Install GitHub Desktop

Download GitHub Desktop from:

`https://desktop.github.com/`

Open it and sign in with your GitHub account.

### 3. Clone your existing repository

In GitHub Desktop:

1. Choose **File → Clone repository**.
2. Select `JeroenMonnee/JeroenMonnee.github.io`.
3. Choose a local folder.
4. Click **Clone**.

Your repository currently uses the `master` branch. The included publishing workflow
supports both `master` and `main`.

### 4. Replace the old website files

In GitHub Desktop, choose **Repository → Show in Explorer**.

Inside the repository folder:

1. Delete the old website files and folders.
2. Do **not** delete the hidden `.git` folder.
3. Copy the entire contents of this website package into the repository folder.
4. Make sure `_quarto.yml` is directly inside the repository root, not inside an
   additional nested folder.

The repository root should now contain files such as:

```text
_quarto.yml
index.qmd
research.qmd
publications.qmd
styles.css
theme.scss
.github/
assets/
files/
```

### 5. Commit and push

Return to GitHub Desktop.

1. In the summary field, enter: `Replace Academic Pages with Quarto website`
2. Click **Commit to master**.
3. Click **Push origin**.

### 6. Tell GitHub Pages to use GitHub Actions

On GitHub:

1. Open the repository.
2. Choose **Settings**.
3. In the left sidebar, choose **Pages**.
4. Under **Build and deployment → Source**, select **GitHub Actions**.

### 7. Wait for the first deployment

Open the repository's **Actions** tab.

You should see a workflow called **Publish Quarto website**. It normally takes one or
two minutes. A green check mark means the website was deployed successfully.

Then open:

`https://jeroenmonnee.github.io`

## Updating the website

Every time you push a change, GitHub rebuilds and republishes the website automatically.

### Quick edits directly on GitHub

For a small text change:

1. Open the relevant `.qmd` file on GitHub.
2. Click the pencil icon.
3. Edit the text.
4. Click **Commit changes**.

The site will update automatically after the workflow finishes.

### Larger edits on your computer

For local previewing:

1. Install Quarto from `https://quarto.org/docs/download/`.
2. Optionally install Visual Studio Code and the Quarto extension.
3. Open the repository folder.
4. Run:

```bash
quarto preview
```

A browser window will open and refresh when you save a file.

After editing, use GitHub Desktop to commit and push.

## Where to edit what

| Change | File |
|---|---|
| Homepage text | `index.qmd` |
| Research programme | `research.qmd` |
| Publications | `publications.qmd` |
| Talks and service | `activities.qmd` |
| Teaching and supervision | `teaching.qmd` |
| Navigation and social links | `_quarto.yml` |
| Main colours and fonts | `theme.scss` |
| Layout and visual details | `styles.css` |
| CV PDF | `files/Jeroen_Monnee_CV.pdf` |
| Homepage illustration | `assets/research-geometry.svg` |

## Updating the CV

Replace `files/Jeroen_Monnee_CV.pdf` with the new PDF, keeping the same filename.
No other file needs to be changed.

## Changing the main colours

Open `theme.scss`. The first lines contain:

```scss
$primary: #17324d;
$secondary: #1d7a78;
$warning: #c79a3b;
$body-bg: #fbfaf7;
```

Changing those hexadecimal colour values changes the site's overall palette.

The matching reusable colour variables also appear at the top of `styles.css`.

## Common problem: the old site still appears

Check:

1. **Settings → Pages → Source** is set to **GitHub Actions**.
2. The latest workflow under **Actions** has a green check mark.
3. You copied the website files into the repository root.
4. You pushed the commit to `master` or `main`.
5. Refresh the site with `Ctrl+F5`.

## Common problem: the workflow failed

Open the failed workflow under **Actions**, click the failed step, and read the error.
Most errors are caused by:

- invalid indentation in `_quarto.yml`;
- a missing quotation mark;
- an unclosed HTML tag in a `.qmd` file;
- accidentally renaming or deleting a referenced file.

The original files in this package give you a clean version to restore.
