# Lab Website Update Guide
## Ben-Zion Resilience & Recovery Lab

**Website URL:** https://zivbz1.github.io/benzion-lab/
**GitHub Repo:** https://github.com/zivbz1/benzion-lab

---

## How to Edit the Website

### Option A: Edit Directly on GitHub (Easiest)

1. Go to: https://github.com/zivbz1/benzion-lab/blob/main/index.html
2. Click the **pencil icon** (Edit this file) in the top-right
3. Make your changes (see templates below)
4. Scroll down, write a short description (e.g., "Add new publication")
5. Click **"Commit changes"**
6. The website updates automatically within 1-2 minutes

### Option B: Edit Locally + Push

1. Open `index.html` in VS Code or any text editor
2. Make your changes
3. Open terminal in the `lab-website` folder and run:
```bash
git add index.html
git commit -m "Description of change"
git push
```

---

## Common Updates

### Add a New Publication

Find the `<!-- Publications -->` section. Locate the correct year header (e.g., `<div class="pub-year fade-in">2025</div>`). Paste this template **below the year header**:

```html
        <div class="pub-card fade-in">
          <img class="pub-journal-img" src="JOURNAL_IMAGE_URL" alt="Journal">
          <div>
            <h4>Paper Title Here</h4>
            <div class="pub-meta">
              <span>Author1, Author2, et al.</span><br>
              <span class="pub-journal">Journal Name</span><span class="pub-if">IF X.X</span>
            </div>
          </div>
          <a href="https://doi.org/YOUR_DOI_HERE" target="_blank" class="pub-link" title="View paper"><i class="ri-external-link-line"></i></a>
        </div>
```

**Replace:**
- `JOURNAL_IMAGE_URL` - URL of journal cover image (see list below)
- `Paper Title Here` - full paper title
- `Author1, Author2, et al.` - author list
- `Journal Name` - name of the journal
- `IF X.X` - impact factor
- `YOUR_DOI_HERE` - the DOI link

**Common journal image URLs:**
- Nature: `https://campuspress.yale.edu/zivbenzion/files/2025/07/Capture.png`
- Biological Psychiatry: `https://campuspress.yale.edu/zivbenzion/files/2025/11/cover.tif_.jpg`
- JAMA Network Open: `https://dladata.com/img/products/2/jamano.png`
- Molecular Psychiatry: `https://campuspress.yale.edu/zivbenzion/files/2023/07/Molecular_Psychiatry.gif`
- AJP: `https://campuspress.yale.edu/zivbenzion/files/2023/07/AJP.png`
- EJPT: `https://campuspress.yale.edu/zivbenzion/files/2023/07/EJPT.jpg`
- BP CNNI: `https://campuspress.yale.edu/zivbenzion/files/2023/07/BP-CNNI.jpg`
- npj Digital Medicine: `https://pbs.twimg.com/profile_images/1875721159867609089/KTHJ-x7M_400x400.jpg`
- Annual Review of Psychology: `https://campuspress.yale.edu/zivbenzion/files/2024/06/AR-Psychology.jpg`
- Frontiers in Psychiatry: `https://campuspress.yale.edu/zivbenzion/files/2024/12/Frontiers-Psychiatry.jpg`
- JAD: `https://campuspress.yale.edu/zivbenzion/files/2023/07/JAD-1.jpg`
- JPR: `https://campuspress.yale.edu/zivbenzion/files/2023/07/JPR.jpg`
- Translational Psychiatry: `https://campuspress.yale.edu/zivbenzion/files/2023/07/Translational-Psychiatry.jpg`
- NeuroImage: `https://campuspress.yale.edu/zivbenzion/files/2023/07/Neuroimage.gif`

**To add a new year**, insert this before the first publication of that year:
```html
        <div class="pub-year fade-in">2026</div>
```

---

### Add a News Item

Find the `<!-- News & Media -->` section. Add inside `<div class="news-grid">`:

```html
        <div class="news-card fade-in">
          <span class="news-date">Month Year</span>
          <h4>Headline Here</h4>
          <p>Short description of the news item.</p>
          <a href="https://link-to-article.com" target="_blank">Source Name <i class="ri-arrow-right-line"></i></a>
        </div>
```

Keep 6 items maximum. Remove the oldest one when adding a new one.

---

### Add a Team Member

Find the `<div class="team-grid">` section. Add a new card:

```html
        <div class="team-card fade-in">
          <div class="team-photo"><i class="ri-user-line"></i></div>
          <h4>Full Name</h4>
          <div class="role">Role (e.g., MSc Student, PhD Student, Lab Manager)</div>
        </div>
```

Don't forget to update the team count in the statistics banner:
Find `data-target="7"` (under "Team Members") and change the number.

---

### Add a Collaborator

Find the `<!-- Collaborations -->` section. Add inside `<div class="collab-grid">`:

```html
        <div class="collab-card fade-in">
          <img class="collab-logo" src="INSTITUTION_LOGO_URL" alt="Institution Name">
          <h4>Collaborator Name</h4>
          <div class="collab-role">Title, Department, Institution</div>
        </div>
```

Update the collaborations count in the statistics banner if needed.

---

### Update Statistics

Find the statistics banner section (search for `stats-banner`). Each stat has a `data-target` attribute:

```html
<div class="stat-number" data-target="36">0</div>  <!-- Publications -->
<div class="stat-number" data-target="7">0</div>   <!-- Team Members -->
<div class="stat-number" data-target="8">0</div>   <!-- Research Projects -->
<div class="stat-number" data-target="25">0</div>  <!-- Collaborations -->
```

Change the number in `data-target="X"` to update.

---

### Add an Image

1. Add the image file to the GitHub repo (drag & drop on the repo page, or git add + push)
2. Reference it in HTML as: `src="filename.jpg"`
3. For team member photos, replace `<i class="ri-user-line"></i>` with `<img src="photo.jpg" alt="Name" style="width:100%;height:100%;object-fit:cover">`

---

## Important Notes

- Always test your changes by viewing the website after committing
- Use `&amp;` instead of `&` in HTML text (e.g., `Resilience &amp; Recovery`)
- Keep the `fade-in` class on new elements for scroll animations
- Add `target="_blank"` to external links so they open in a new tab