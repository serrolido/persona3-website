# Persona 3 Website

A modern, interactive website built with React and Vite, featuring smooth animations powered by Framer Motion and seamless navigation using React Router.

## Table of Contents

- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Project Setup](#project-setup)
- [Available Commands](#available-commands)
- [Development Workflow](#development-workflow)
- [Building for Production](#building-for-production)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Troubleshooting](#troubleshooting)

## System Requirements

Before you begin, ensure you have the following installed on your system:

- **Node.js** (version 18 or higher)
  - Download from: [nodejs.org](https://nodejs.org/)
  - Verify installation: Run `node --version` in your terminal
  
- **npm** (comes with Node.js)
  - Verify installation: Run `npm --version` in your terminal

- **Git** (optional, but recommended for version control)
  - Download from: [git-scm.com](https://git-scm.com/)

## Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/persona3-website.git
cd persona3-website
```

*Or if you have the project folder already, navigate to it:*

```bash
cd persona3-website
```

### Step 2: Install Dependencies

Install all required npm packages:

```bash
npm install
```

This command will:
- Read the `package.json` file
- Download and install all dependencies listed in `dependencies` and `devDependencies`
- Create a `node_modules` folder
- Generate a `package-lock.json` file for dependency management

### Step 3: Verify Installation

Verify that everything is set up correctly:

```bash
npm run lint
```

This checks your code for any linting errors.

## Project Setup

### Environment Configuration

The project uses Vite with React and requires no additional environment setup. However, if you need to configure environment variables:

1. Create a `.env` file in the project root
2. Add your variables using the format: `VITE_YOUR_VAR_NAME=value`
3. Access them in your code using: `import.meta.env.VITE_YOUR_VAR_NAME`

### Project Initialization

The project is pre-configured with:
- **Vite**: Fast build tool and dev server
- **React 19**: Latest React version for UI components
- **React Router 7**: Client-side routing
- **Framer Motion**: Advanced animation library
- **ESLint**: Code quality and style checking

## Available Commands

### `npm run dev`

Start the development server with hot module replacement (HMR):

```bash
npm run dev
```

- Launches a local development server (typically at `http://localhost:5173`)
- Automatically reloads the browser when you save files
- Provides fast feedback during development

### `npm run build`

Build the project for production:

```bash
npm run build
```

- Compiles React components and optimizes assets
- Minifies code for smaller file sizes
- Generates optimized output in the `dist/` folder
- Ready for deployment

### `npm run build:watch`

Build the project and watch for changes:

```bash
npm run build:watch
```

- Rebuilds the project whenever source files change
- Useful for monitoring builds during development
- Generated files appear in the `dist/` folder

### `npm run preview`

Preview the production build locally:

```bash
npm run preview
```

- Serves the built files from the `dist/` folder
- Tests production build locally before deployment
- Useful for verifying build output before deploying

### `npm run lint`

Check code quality with ESLint:

```bash
npm run lint
```

- Identifies code style issues and potential errors
- Runs according to the `.eslintrc` configuration

## Development Workflow

### Quick Start

1. **Install dependencies** (first time only):
   ```bash
   npm install
   ```

2. **Start the development server**:
   ```bash
   npm run dev
   ```

3. **Open in browser**:
   - Navigate to `http://localhost:5173` (or the URL shown in terminal)
   - The page will automatically reload as you edit files

4. **Edit and save**:
   - Modify React components in the `src/` folder
   - See changes instantly in your browser with HMR

### Development Tips

- **Hot Module Replacement**: Changes to `.jsx` and `.css` files reload instantly
- **Console Errors**: Check your browser's console (F12) for React warnings and errors
- **Terminal Output**: Watch the terminal for build errors and Vite messages
- **Vite Dev Tools**: Take advantage of the Vite client's debugging features

## Building for Production

### Production Build Process

1. **Build the project**:
   ```bash
   npm run build
   ```

2. **Output Location**: 
   - Compiled files are created in the `dist/` folder
   - Ready to deploy to any static hosting service

3. **Preview the build** (optional):
   ```bash
   npm run preview
   ```

4. **Deploy**: 
   - Upload the contents of the `dist/` folder to your hosting service (Netlify, Vercel, GitHub Pages, etc.)

### Build Optimization

The build process automatically:
- Minifies JavaScript and CSS
- Optimizes images and assets
- Creates chunked bundles for better loading
- Removes development-only code

## Project Structure

```
persona3-website/
├── src/
│   ├── App.jsx                 # Main App component
│   ├── App.css                 # App styling
│   ├── main.jsx                # React DOM entry point
│   ├── index.css               # Global styles
│   ├── AboutMe.jsx             # About page component
│   ├── P3Menu.jsx              # Menu component
│   ├── PageTransition.jsx       # Page transition component
│   ├── ResumePage.jsx           # Resume page component
│   ├── Socials.jsx              # Social media component
│   ├── VideoPage.jsx            # Video page component
│   ├── FontPreview.jsx          # Font preview component
│   └── assets/                  # Static assets (images, etc.)
├── public/                      # Public static files
├── scripts/
│   └── watch-build.mjs          # Build watch script
├── index.html                   # HTML entry point
├── package.json                 # Project dependencies and scripts
├── vite.config.js               # Vite configuration
├── eslint.config.js             # ESLint configuration
└── README.md                    # This file
```

## Technologies Used

| Technology | Version | Purpose |
|------------|---------|---------|
| **React** | 19.2.4 | UI library |
| **Vite** | 8.0.1 | Build tool & dev server |
| **React Router** | 7.14.0 | Client-side routing |
| **Framer Motion** | 12.38.0 | Animation library |
| **ESLint** | 9.39.4 | Code linting |
| **Node.js** | 18+ | JavaScript runtime |

## Troubleshooting

### Issue: `npm install` fails

**Solutions**:
- Clear npm cache: `npm cache clean --force`
- Delete `node_modules` folder: `rm -rf node_modules` (or `rmdir /s node_modules` on Windows)
- Delete `package-lock.json`
- Reinstall: `npm install`
- Try with `npm install --legacy-peer-deps` if there are peer dependency conflicts

### Issue: Dev server won't start (`npm run dev` fails)

**Solutions**:
- Check if port 5173 is in use: `netstat -an | findstr :5173` (Windows) or `lsof -i :5173` (Mac/Linux)
- Use a different port: `npm run dev -- --port 3000`
- Ensure all dependencies are installed: `npm install`
- Clear Vite cache: Delete `.vite` folder and try again

### Issue: "Module not found" error

**Solutions**:
- Ensure all dependencies are installed: `npm install`
- Check import paths are correct and files exist
- Clear `node_modules` and reinstall if needed

### Issue: Changes not reflecting in browser

**Solutions**:
- Hard refresh browser: `Ctrl+Shift+R` (Windows/Linux) or `Cmd+Shift+R` (Mac)
- Check that dev server is running: `npm run dev`
- Verify the correct local URL in browser (usually `http://localhost:5173`)
- Restart the dev server: Stop (Ctrl+C) and run `npm run dev` again

### Issue: Build fails with "dist" folder errors

**Solutions**:
- Delete existing `dist` folder: `rm -rf dist` (or `rmdir /s dist` on Windows)
- Rebuild: `npm run build`
- Check for syntax errors in your code
- Run `npm run lint` to identify code issues

### Port Already in Use

If port 5173 is already in use, start dev server on a different port:

```bash
npm run dev -- --port 3000
```

Or kill the process using the port:

**Windows**:
```bash
netstat -ano | findstr :5173
taskkill /PID <PID> /F
```

**Mac/Linux**:
```bash
lsof -i :5173
kill -9 <PID>
```

## Getting Help

- Check Vite documentation: [vite.dev](https://vite.dev/)
- React documentation: [react.dev](https://react.dev/)
- React Router docs: [reactrouter.com](https://reactrouter.com/)
- Framer Motion docs: [framer.com/motion](https://www.framer.com/motion/)

---

**Happy coding!** 🚀
