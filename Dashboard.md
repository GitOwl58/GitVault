---
cssclasses:
  - dashboard-full-width
  - hide-properties
---

<h1 class="gitvault-title">GitVault</h1>
```dataviewjs
const sections = [
  { name: "Concepts", path: "Concepts" },
  { name: "Pre-Security", path: "Courses/TryHackMe/Pre-Security" },
  { name: "Cyber Security 101", path: "Courses/TryHackMe/Cyber Security 101" },
  { name: "MOCs", path: "MOCs" },
  {name: "Python", path: "Courses/FreeCodecamp/Python"},
  { name: "Linux Fundamentals", path: "Courses/HackTheBox/Linux Fundamentals" },
];

function naturalSort(a, b) {
  return a.file.name.localeCompare(b.file.name, undefined, { numeric: true, sensitivity: "base" });
}

let html = `<div class="dashboard-wrap"><div class="dashboard-grid">`;

for (const section of sections) {
  const pages = dv.pages(`"${section.path}"`).array().sort(naturalSort);

  html += `<div class="dashboard-card"><h3>${section.name}</h3><ul>`;
  for (const p of pages) {
    html += `<li><a href="${p.file.path}" class="internal-link">${p.file.name}</a></li>`;
  }
  html += `</ul></div>`;
}

html += `</div></div>`;
dv.paragraph(html);
```

