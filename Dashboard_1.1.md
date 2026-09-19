---
cssclasses:
  - dashboard-full-width
  - hide-properties
  - gitowl-note
---

<h1 class="gitvault-title">GitVault <span style="font-size:0.35em; opacity:0.55; font-weight:600;">v1.1</span></h1>

```dataviewjs
const sections = [
  { name: "Concepts", path: "Concepts" },
  { name: "Courses", path: "Courses" },
  { name: "MOCs", path: "MOCs" },
  { name: "Homelabbing", path: "Homelabbing" },
];

if (!document.getElementById("dv11-dashboard-style")) {
  const style = document.createElement("style");
  style.id = "dv11-dashboard-style";

  const bannerFile = app.vault.getAbstractFileByPath("Private/Claude Outputs/GitOwl-banner-full.png");
  const bannerUrl = bannerFile ? app.vault.adapter.getResourcePath(bannerFile.path) : "";
  const bannerCss = bannerUrl
    ? `
      .gitowl-note .markdown-preview-view,
      .gitowl-note.markdown-source-view .cm-scroller {
        background-image: linear-gradient(rgba(30,26,46,0.1), rgba(30,26,46,0.32) 55%, rgba(30,26,46,0.44)), url('${bannerUrl}') !important;
        background-size: cover !important;
        background-position: left top !important;
        background-repeat: no-repeat !important;
      }
    `
    : "";

  style.textContent = `
    ${bannerCss}
    .dv11-card {
      background: rgba(45, 38, 64, 0.45);
    }
    .dv11-count {
      font-size: 0.72em;
      opacity: 0.5;
      font-weight: 500;
      margin-left: 4px;
    }
    .dv11-card > ul { margin-top: 0; }
    details.dv11-subfolder, details.dv11-files {
      margin: 2px 0 6px 0;
    }
    details.dv11-subfolder > summary, details.dv11-files > summary {
      cursor: pointer;
      font-size: 0.85em;
      font-weight: 600;
      opacity: 0.85;
      padding: 4px 0;
      list-style: none;
    }
    details.dv11-subfolder > summary::-webkit-details-marker,
    details.dv11-files > summary::-webkit-details-marker { display: none; }
    details.dv11-subfolder > summary::before,
    details.dv11-files > summary::before {
      content: "▸";
      display: inline-block;
      margin-right: 6px;
      transition: transform 0.15s ease;
      color: var(--text-accent);
    }
    details.dv11-subfolder[open] > summary::before,
    details.dv11-files[open] > summary::before {
      transform: rotate(90deg);
    }
    .dv11-nested {
      margin-left: 16px;
      border-left: 1px solid var(--background-modifier-border);
      padding-left: 12px;
    }
    .dv11-card:nth-child(6) h3 { color: #8fd8c9; }
    .dv11-card:nth-child(7) h3 { color: #e07a9e; }
  `;
  document.head.appendChild(style);
}

function naturalSort(a, b) {
  return a.localeCompare(b, undefined, { numeric: true, sensitivity: "base" });
}

function isFolder(f) {
  return f.children !== undefined;
}

function getSubfolders(folder) {
  return folder.children.filter(isFolder).sort((a, b) => naturalSort(a.name, b.name));
}

function getMdFiles(folder) {
  return folder.children
    .filter((c) => !isFolder(c) && c.extension === "md")
    .sort((a, b) => naturalSort(a.basename, b.basename));
}

function countAllFiles(folder) {
  let n = 0;
  for (const c of folder.children) {
    if (isFolder(c)) n += countAllFiles(c);
    else if (c.extension === "md") n += 1;
  }
  return n;
}

function renderFileList(files) {
  const items = files
    .map((f) => `<li><a href="${f.path}" class="internal-link">${f.basename}</a></li>`)
    .join("");
  return `<details class="dv11-files"><summary>${files.length} notes</summary><ul>${items}</ul></details>`;
}

function renderFolder(folder) {
  let html = "";
  const files = getMdFiles(folder);
  const subfolders = getSubfolders(folder);

  if (files.length) {
    html += renderFileList(files);
  }

  for (const sub of subfolders) {
    const subCount = countAllFiles(sub);
    html += `<details class="dv11-subfolder">`;
    html += `<summary>${sub.name}<span class="dv11-count">${subCount}</span></summary>`;
    html += `<div class="dv11-nested">${renderFolder(sub)}</div>`;
    html += `</details>`;
  }

  if (!files.length && !subfolders.length) {
    html += `<p style="opacity:0.5; font-size:0.85em;">empty</p>`;
  }

  return html;
}

let html = `<div class="dashboard-wrap"><div class="dashboard-grid">`;

for (const section of sections) {
  const folder = app.vault.getAbstractFileByPath(section.path);
  html += `<div class="dashboard-card dv11-card"><h3>${section.name}`;
  if (folder) {
    html += `<span class="dv11-count">${countAllFiles(folder)}</span>`;
  }
  html += `</h3>`;
  html += folder
    ? renderFolder(folder)
    : `<p style="opacity:0.5; font-size:0.85em;">folder not found: ${section.path}</p>`;
  html += `</div>`;
}

html += `</div></div>`;
dv.paragraph(html);
```











