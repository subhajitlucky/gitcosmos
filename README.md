# GitCosmos - Git & Version Control Visualizer

A premium, visual-first educational platform that teaches Git and Version Control concepts through interactive animations, commit graph visualizations, and a fully simulated Git engine.

![GitCosmos](https://img.shields.io/badge/GitCosmos-Visual%20Git%20Learning-blue)

## Features

- **Interactive Git Playground** - Safely experiment with Git operations (commit, branch, merge, rebase, reset, etc.) in a risk-free environment
- **Visual Commit Graphs** - See commits, branches, and merge relationships in an intuitive SVG-based visualization
- **Comprehensive Concept Guide** - Learn Git fundamentals to advanced workflows with clear explanations and animations
- **Dark/Light Theme** - Toggle between themes with preference persistence
- **Fully Simulated Git Engine** - Client-side Git simulation that accurately models Git behavior

## How Git is Simulated

GitCosmos implements a complete Git simulation engine that accurately models Git's internal mechanics:

### Core Git Model

1. **Commits as Immutable Snapshots**
   - Each commit is stored as a complete snapshot of the project state
   - Commits are immutable - once created, they never change
   - Each commit has a unique SHA-1 hash identifier

2. **Branches as Pointers**
   - Branches are lightweight references pointing to specific commits
   - Creating a branch creates a new 41-byte file with a commit hash
   - Branches move forward as new commits are made

3. **HEAD Pointer**
   - HEAD points to the current branch or commit you're viewing
   - Attached HEAD: points to a branch reference
   - Detached HEAD: points directly to a commit hash

4. **Merges**
   - Fast-forward merges: simply move the branch pointer forward
   - Three-way merges: create a new merge commit with two parent commits
   - Merge commits have multiple parent references

5. **Rebase**
   - Creates new commits with new hashes
   - Moves commits to a new base commit
   - Rewrites history linearly

## Installation & Setup

### Prerequisites

- Node.js 18+ and npm/yarn/pnpm

### Installation

```bash
# Clone or navigate to the project directory
cd gitcosmos

# Install dependencies
npm install

# Start the development server
npm run dev
```

The app will be available at `http://localhost:5173`

### Building for Production

```bash
# Build the app
npm run build

# Preview the production build
npm run preview
```

## Project Structure

```
gitcosmos/
├── src/
│   ├── components/      # Reusable React components
│   │   ├── Layout.jsx   # Main app layout with navbar
│   │   ├── CommitGraph.jsx  # SVG-based commit graph visualization
│   │   └── InspectorPanel.jsx  # Git state inspector
│   ├── context/         # React contexts
│   │   └── ThemeProvider.jsx   # Dark/light theme management
│   ├── data/            # Static data
│   │   └── concepts.js         # All Git concept definitions
│   ├── lib/             # Utility functions
│   │   └── utils.js            # Helper functions
│   ├── pages/           # Page components
│   │   ├── Home.jsx           # Landing page
│   │   ├── ConceptMap.jsx     # Overview of all concepts
│   │   ├── ConceptPage.jsx     # Individual concept details
│   │   └── Playground.jsx     # Interactive Git playground
│   └── store/           # State management
│       └── gitStore.jsx        # Zustand store for Git engine
├── public/              # Static assets
├── index.html           # HTML entry point
├── package.json         # Dependencies and scripts
├── tailwind.config.js   # TailwindCSS configuration
└── vite.config.js       # Vite configuration
```

## Tech Stack

- **React 18** - UI framework
- **Vite** - Build tool and dev server
- **TailwindCSS** - Utility-first CSS framework
- **Framer Motion** - Animation library
- **Zustand** - State management
- **React Router** - Client-side routing
- **Lucide React** - Icon library

## Key Concepts Covered

### Git Fundamentals
- What is Version Control
- Git vs Other VCS
- Repository
- Working Directory
- Staging Area (Index)
- Commit
- Commit Hash
- Snapshots vs Diffs

### Branches & HEAD
- HEAD
- Branch
- Checkout
- Detached HEAD
- Log & History

### Merging & Rebasing
- Merge
- Fast-forward Merge
- Three-way Merge
- Merge Conflicts
- Rebase
- Rebase vs Merge

### Undoing Changes
- Reset (soft, mixed, hard)
- Revert
- Stash

### Remote Repositories
- Remote Repositories
- Origin & Upstream
- Fetch vs Pull
- Push
- Pull Requests (Conceptual)

### Advanced Git
- Cherry-pick
- Bisect (Conceptual)
- Tags
- Git Internals

## Using the Playground

The Git Playground allows you to experiment with Git operations:

### Basic Operations

1. **Create Commits**
   - Enter a commit message and click "Commit"
   - Each commit becomes a new node in the graph

2. **Create Branches**
   - Enter a branch name and click the + button
   - The branch pointer appears on the current commit

3. **Checkout Branches**
   - Select a branch and click "Checkout"
   - HEAD moves to that branch

4. **Merge Branches**
   - Select a branch to merge from
   - Watch as Git performs either a fast-forward or three-way merge

5. **Rebase**
   - Select a target branch to rebase onto
   - See commits rewrite with new hashes

6. **Reset**
   - Choose soft, mixed, or hard reset
   - Watch the HEAD pointer move backwards

7. **Tag**
   - Create tags on the current commit
   - Tags appear as labels on the commit graph

### Undo/Redo

The playground supports full undo/redo functionality, allowing you to explore different Git workflows without consequences.

## Limitations of the Visual Engine

This is a **simulation**, not actual Git. Key limitations:

1. **No File Content**
   - The engine tracks commits and relationships only
   - There's no actual file content or staging area
   - "Staging" is conceptual only

2. **Simplified Merge Conflict Resolution**
   - Merge conflicts are detected but not resolved interactively
   - In real Git, you'd manually edit conflicted files

3. **No Remote Operations**
   - Fetch, pull, and push are conceptual only
   - No actual network operations occur

4. **Simplified Rebase**
   - Interactive rebase features are not implemented
   - Conflict handling during rebase is simplified

5. **Hash Generation**
   - Commits use simplified hashes, not real SHA-1
   - Hash generation doesn't account for all Git metadata

6. **Git Internals Abstraction**
   - Blobs, trees, and objects are modeled conceptually
   - No actual Git object database

7. **No Branch Protection**
   - Protected branches and force push restrictions are not modeled

Despite these limitations, the simulation accurately teaches Git's core mental model: commits as immutable nodes, branches as pointers, and HEAD as a "you are here" marker.

## Educational Goals

GitCosmos is designed to help you:

1. **Build a correct mental model** of how Git works internally
2. **See commits, branches, and HEAD movement** visually
3. **Understand Git as a graph** and pointer system, not magic commands
4. **Experiment safely** with Git operations
5. **Demystify common Git confusion** through animation

## Contributing

This is an educational project focused on visual learning. Contributions that improve the Git simulation accuracy, add more concept visualizations, or enhance the interactive playground are welcome.

## License

MIT License - feel free to use this for educational purposes.

## Acknowledgments

- Inspired by Learn Git Branching and other visual Git learning tools
- Built with modern web technologies for optimal learning experience
- Designed to make Git intuitive through visualization