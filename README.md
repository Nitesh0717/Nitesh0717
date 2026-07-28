<div align="center">

<!-- Animated Header Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:00ff88,100:00bfff&height=220&section=header&text=Nitesh%20Singh&fontSize=50&fontColor=ffffff&animation=twinkling" width="100%" />

<!-- Profile Avatar Graphic -->
<a href="https://github.com/Nitesh0717">
  <img src="https://itshivam.in/api/github-image?username=Nitesh0717" height="180" style="border-radius: 50%;" alt="Nitesh Singh Graphic" />
</a>

<br/>

<!-- Animated Typing Subtitle -->
<h3>
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=1000&color=00FF88&center=true&vCenter=true&width=700&lines=Full+Stack+Developer;Cloud+%26+DevOps+Engineer;Building+Scalable+Cloud+Native+Systems" alt="Typing SVG" />
</h3>

<!-- Social Badges -->
<p align="center">
  <a href="https://linkedin.com/in/nitesh-singh-23a22a250" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="mailto:nitesh.03ns@gmail.com" target="_blank">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" />
  </a>
  <a href="https://www.leetcode.com/Nitesh_04" target="_blank">
    <img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=LeetCode&logoColor=black" alt="LeetCode" />
  </a>
</p>

<!-- Overview Metrics Card -->
<p align="center">
  <a href="https://github.com/Nitesh0717">
    <img src="https://itshivam.in/api/github-profile?username=Nitesh0717&data=followers,repositories,stars,commits&theme=neon" width="85%" alt="Profile Metrics" />
  </a>
</p>

</div>

---

## 🚀 About Me

- 🔭 **In Flight Focus:** Actively designing distributed cloud-native architectures and dynamic microservices monitoring hubs.
- 👯 **Collaboration Targets:** Open-source platform tools, CI/CD automation frameworks, and cloud infrastructure tooling.
- 💬 **Core Consultations:** Ask me about containerized pipelines with **Docker**, cluster orchestrations with **Kubernetes**, or structuring resilient **AWS** environments.
- 📫 **Reach Me:** Drop a line at `nitesh.03ns@gmail.com` to discuss cloud scalability or infrastructure projects.

---

## 🧠 Core Competencies & Tech Stack

| Category | Technologies & Tools |
| :--- | :--- |
| **Cloud & DevOps** | <img src="https://skillicons.dev/icons?i=aws,docker,kubernetes,linux,jenkins,terraform,ansible,git,githubactions" /> |
| **Languages** | <img src="https://skillicons.dev/icons?i=java,python,js,ts" /> |
| **Backend & Databases** | <img src="https://skillicons.dev/icons?i=node,express,mongodb,mysql" /> |
| **Frontend Frameworks** | <img src="https://skillicons.dev/icons?i=react,vite,tailwind,html,css,bootstrap" /> |

---

## 📈 Live Contribution Activity

<!-- Live Contribution Snake Animation -->
<p align="center">
  <img src="https://raw.githubusercontent.com/Nitesh0717/Nitesh0717/output/github-contribution-grid-snake.svg" alt="Snake Animation" width="100%" />
</p>

<!-- Live GitHub Stats Metrics -->
<div align="center">
  <a href="https://github.com/Nitesh0717">
    <img src="https://github-readme-stats.vercel.app/api?username=Nitesh0717&show_icons=true&theme=dark&bg_color=0D1117&text_color=00FF88&icon_color=00FF88&title_color=ffffff&border_color=30363d" width="48%" alt="GitHub Stats" />
  </a>
  <a href="https://github.com/Nitesh0717">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Nitesh0717&layout=compact&theme=dark&bg_color=0D1117&text_color=00FF88&icon_color=00FF88&title_color=ffffff&border_color=30363d" width="48%" alt="Top Languages" />
  </a>
</div>

<br/>

<blockquote align="center">
  <i>"Simplicity is the soul of efficiency." — Built to automate, orchestrate, and scale.</i>
</blockquote>

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:00bfff,50:00ff88,100:0d1117&height=100&section=footer" width="100%" />
</div>

name: generate animation

on:
  schedule:
    - cron: "0 */12 * * *" 
  workflow_dispatch:
  push:
    branches:
    - main

jobs:
  generate:
    permissions: 
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    
    steps:
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
            
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages-action@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
