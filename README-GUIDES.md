# Guide for use readme.md

Welcome to the guide for setting up and customizing a dynamic GitHub profile like the one at https://github.com/arcxteam/arcxteam. This guide helps you configure the snake animation, GitHub statistics, technology badges, and a link to the `README-GUIDES.md` file. It’s designed for users forking your repository to create their own personalized profile design.

## Prerequisites
- An active GitHub account.
- A public repository for your profile (e.g., `username/username`).
- GitHub Actions enabled for workflows.
- Basic knowledge of Markdown and YAML.

## Displaying the Snake Animation
1. **Ensure Workflow is Active**:
   - The `.github/workflows/snake.yml` file must exist in your repository. This workflow generates animation files in the `assets/` folder.
   - Generated files:
     - `github-snake.svg` (light mode)
     - `github-snake-dark.svg` (dark mode)
     - `custom-snake.gif` (animated GIF)
2. **Add Animation to README.md**:
   - Add the following code to your `README.md` to display the GIF animation:
     ```markdown
     ![Custom Snake GIF](https://raw.githubusercontent.com/[username]/[repo]/main/assets/custom-snake.gif)
     ```
     - Replace `[username]` and `[repo]` with your GitHub username and repository name (e.g., `arcxteam/arcxteam`).
3. **Commit Changes**:
   - Use the commit message `Update snake animation 🐍`.
   - Run the workflow manually in the **Actions** tab to generate animation files.
4. **Verify**:
   - Visit your GitHub profile (https://github.com/[username]) to ensure the animation appears in your README.

## Customizing Colors and Themes
Customize the snake animation by editing `snake.yml`:
- **Snake Color**: Modify `color_snake` in the `outputs` section. Examples:
  - `#FEF000` (yellow)
  - `#00FF00` (green)
  - `#FF00FF` (magenta)
- **Contribution Dot Colors**: Add `color_dots` for a gradient (optional). Example: `color_dots=#800080,#A052FF,#D8B2FF,#E6D8FF,#F0E6FF` (purple gradient).
- **Background Theme**: Use `palette` for specific themes:
  - `palette=github-dark` (dark mode)
  - `palette=github-light` (light mode, default)
  - Leave blank for a default contribution-based theme.
- **Example Configuration**:
  ```yaml
  - name: Generate Snake Animations
    uses: Platane/snk@v3
    with:
      github_user_name: ${{ github.repository_owner }}
      outputs: |
        assets/github-snake.svg?color_snake=#FEF000&palette=github-dark
        assets/github-snake-dark.svg?color_snake=#FEF000&palette=github-dark
        assets/custom-snake.gif?color_snake=#FEF000&color_dots=#800080,#A052FF,#D8B2FF,#E6D8FF,#F0E6FF&palette=github-dark
  ```
- **Customization Steps**:
  1. Edit `snake.yml` in `.github/workflows/`.
  2. Commit with the message `Update snake animation!`.
  3. Run the workflow in **Actions** to update animations.
  4. Check the results in your `README.md`.

## Adding GitHub Statistics
Enhance your README with statistics like top languages, profile stats, and contribution streaks:
1. **Top Languages**:
   - Use `github-readme-stats` to display frequently used languages:
     ```markdown
     ![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=[username]&layout=compact&theme=dark&bg_color=0d1116&title_color=8A2BE2&text_color=fef000&icon_color=fef000&hide_border=true&card_width=470)
     ```
     - Replace `[username]` with your GitHub username.
2. **GitHub Stats**:
   - Show stats like total commits and stars:
     ```markdown
     ![GitHub Stats](https://github-readme-stats.vercel.app/api?username=[username]&hide=contribs,prs&show_icons=true&bg_color=0d1116&title_color=8a2be2&text_color=fef000&icon_color=8a2be2&hide_border=true)
     ```
3. **GitHub Streak**:
   - Display your contribution streak:
     ```markdown
     ![GitHub Streak](https://github-readme-streak-stats.herokuapp.com?user=[username]&theme=yellowdark&date_format=j%20M%5B%20Y%5D&card_width=470&card_height=120&background=000000)
     ```
4. **Contribution Graph**:
   - Add an activity graph:
     ```markdown
     ![Contribution Graph](https://github-readme-activity-graph.vercel.app/graph?username=[username]&bg_color=0d1116&color=fef000&line=8a2be2&point=fef000&area=true&hide_border=true)
     ```

## Adding Technology Badges
Showcase your skills with technology badges:
- Example badges from your `README.md`:
  ```markdown
  ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
  ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
  ![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=fef000)
  ![Astro](https://img.shields.io/badge/Astro-ff8c00?style=for-the-badge&logo=astro&logoColor=black)
  ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
  ![Shell Script](https://img.shields.io/badge/Shell_Script-66ff00?style=for-the-badge&logo=gnu-bash&logoColor=black)
  ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
  ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
  ![Solidity](https://img.shields.io/badge/Solidity-e6e6e6?style=for-the-badge&logo=solidity&logoColor=black)
  ```
- **Customizing Badges**:
  - Use https://shields.io/ to create new badges.
  - Adjust colors (`color`), logos (`logo`), and labels (`label`) to match your skills.
  - Example: Add a Node.js badge:
    ```markdown
    ![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
    ```

## Adding a Link to README-GUIDES
To include a clickable link to your `README-GUIDES.md` file, styled like the original profile:
1. Add the following code to your `README.md`:
   ```markdown
   
     
       
     
   
   ```
   - Replace `[username]/[repo]` with your GitHub username and repository name (e.g., `arcxteam/arcxteam`).
2. Commit with the message `Update profile design!`.
3. Ensure `README-GUIDES.md` exists in the root of your repository. If not, create it (refer to https://github.com/arcxteam/arcxteam/blob/main/README-GUIDES.md for an example).
4. Verify the badge appears in your README and the link directs to `README-GUIDES.md`.

## Setting Up GitHub Pages
If GitHub Pages shows a 404 error or is blank:
1. Go to **Settings > Pages** in your repository:
   - **Source**: Select "Deploy from a branch".
   - **Branch**: Select `main`.
   - **Folder**: Select `/assets`.
2. Click **Save** and wait 1-2 minutes.
3. Check `https://[username].github.io/[repo]` (e.g., `https://arcxteam.github.io/arcxteam`).
4. If still blank:
   - Ensure the `assets/` folder exists in the `main` branch (check https://github.com/[username]/[repo]/tree/main).
   - Re-run the workflow in **Actions** to generate files.

## Forking and Creating Your Own Profile Design
When forking this repository (e.g., from `arcxteam/arcxteam`):
1. **Fork the Repository**:
   - Click **Fork** at https://github.com/arcxteam/arcxteam.
   - Create a new repository in your account (e.g., `[username]/[repo]`).
2. **Customize README.md**:
   - Replace all instances of `arcxteam` with your GitHub username.
   - Update personal details (e.g., “I am currently working as Engineer, Web3 Jobs, Architect”) to reflect your profile.
   - Add unique information like your projects or technologies.
3. **Customize snake.yml**:
   - Update `github_user_name` in `snake.yml` to your GitHub username.
   - Customize snake colors, dots, and themes as described above.
4. **Add Personal Elements**:
   - Include technology badges relevant to your skills.
   - Use `github-readme-stats` with your username for personalized stats.
5. **Commit and Run Workflow**:
   - Commit changes with `Update snake animation!` for animations or `Update profile design 📝` for README updates.
   - Run the workflow in **Actions** to generate new animations.
6. **Verify Profile**:
   - Ensure animations, stats, and badges appear on your GitHub profile.
   - Check GitHub Pages to confirm files in `assets/` are deployed correctly.

## Commit Message Guidelines
- Use `Update snake animation!` for color or theme changes.
- Use `Update profile design!` for README or visual updates.
- Use `Update workflow to push directly to main` for workflow structure changes.

## Additional Notes
- **Remove Old Files**: Delete outdated files like `ocean.gif` in `assets/` via GitHub (select file > three dots > **Delete**).
- **Improve Color Contrast**: If the snake color (#FEF000) or dots (#800080) appear faint, try more vibrant colors like `#FF00FF` for the snake or `#4B0082` for the first dot.
- **Troubleshooting**:
  - If animations don’t appear, check **Actions** logs for errors.
  - If Pages is blank, verify the `/assets` folder setting and ensure files exist in `main`.
  - Share screenshots of **Actions** logs or **Pages** settings if issues persist.
