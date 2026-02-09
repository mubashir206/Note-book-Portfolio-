# 📖 Notebook Portfolio - Mubashir Hussain

A beautiful, interactive **notebook-style portfolio website** built with Vue.js 3 and Tailwind CSS. Your resume is presented as a book with page-flipping animations.

## ✨ Features

- 🎨 **Book-Style Design** - Portfolio presented as an interactive notebook
- 📄 **Page Flipping Animation** - Smooth transitions between pages
- 📱 **Fully Responsive** - Works perfectly on mobile, tablet, and desktop
- ⌨️ **Keyboard Navigation** - Use arrow keys to navigate (Left/Right or Up/Down)
- 🎯 **Clean UI** - Modern design with Tailwind CSS
- 🚀 **Fast Performance** - Built with Vue 3 Composition API

## 📚 Portfolio Pages

1. **Cover Page** - Introduction with name and title
2. **About Me** - Contact information and introduction
3. **Core Competencies** - Technical skills and expertise
4. **Professional Experience** - Work history at Maqware Solutions
5. **Projects (Part 1)** - InkApp and Taif Shipping ERP
6. **Projects (Part 2)** - HRM, Insurance, Asset Management systems
7. **Education** - University and academic background
8. **Back Cover** - Thank you page with call-to-action

## 🛠️ Technologies Used

- **Vue.js 3** - Progressive JavaScript Framework
- **Vite** - Next Generation Frontend Tooling
- **Tailwind CSS** - Utility-First CSS Framework
- **Vue Router** - Official Router for Vue.js
- **Pinia** - State Management

## 🚀 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn

### Installation

1. Clone the repository
\`\`\`bash
git clone <your-repo-url>
cd portfolio
\`\`\`

2. Install dependencies
\`\`\`bash
npm install
\`\`\`

3. Run development server
\`\`\`bash
npm run dev
\`\`\`

4. Open your browser and visit `http://localhost:5173`

### Build for Production

\`\`\`bash
npm run build
\`\`\`

The built files will be in the `dist` directory.

### Preview Production Build

\`\`\`bash
npm run preview
\`\`\`

## 🎮 Navigation

- **Mouse/Touch**: Click "Next" or "Previous" buttons
- **Keyboard**: 
  - `→` or `↓` - Next page
  - `←` or `↑` - Previous page

## 📂 Project Structure

\`\`\`
portfolio/
├── src/
│   ├── assets/
│   │   └── styles/
│   │       └── main.css          # Tailwind & custom styles
│   ├── components/
│   │   ├── NotebookContainer.vue # Main notebook component
│   │   └── pages/                # Individual page components
│   │       ├── CoverPage.vue
│   │       ├── AboutPage.vue
│   │       ├── CompetenciesPage.vue
│   │       ├── ExperiencePage.vue
│   │       ├── ProjectsPage1.vue
│   │       ├── ProjectsPage2.vue
│   │       ├── EducationPage.vue
│   │       └── BackCoverPage.vue
│   ├── views/
│   │   └── HomeView.vue          # Main view
│   ├── router/
│   │   └── index.js              # Route configuration
│   ├── App.vue                   # Root component
│   └── main.js                   # App entry point
├── tailwind.config.js            # Tailwind configuration
├── postcss.config.js             # PostCSS configuration
└── package.json
\`\`\`

## 🎨 Customization

### Update Content

Edit the page components in `src/components/pages/` to update your information:

- `AboutPage.vue` - Contact info and introduction
- `CompetenciesPage.vue` - Skills and technologies
- `ExperiencePage.vue` - Work experience
- `ProjectsPage1.vue` & `ProjectsPage2.vue` - Your projects
- `EducationPage.vue` - Educational background

### Styling

- Main styles: `src/assets/styles/main.css`
- Tailwind config: `tailwind.config.js`
- Component-specific styles: In each `.vue` file's `<style>` section

## 📱 Responsive Breakpoints

- **Mobile**: < 768px (Single page view)
- **Tablet**: 768px - 1024px (Two page view)
- **Desktop**: > 1024px (Full notebook view)

## 🌟 Features to Add (Optional)

- [ ] Add page flip sound effect
- [ ] Bookmark navigation
- [ ] Print to PDF functionality
- [ ] Dark mode toggle
- [ ] Page search functionality
- [ ] Animated page numbers

## 📄 License

This project is open source and available for personal use.

## 👨‍💻 Author

**Mubashir Hussain**
- Email: mh260339i@gmail.com
- Phone: +923480464778
- LinkedIn: Mubashir-Hussain
- Location: Firdous Market, Lahore

---

Built with ❤️ using Vue.js 3 and Tailwind CSS
