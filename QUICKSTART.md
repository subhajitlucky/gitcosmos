# Quick Start Guide

## Running GitCosmos

1. **Install dependencies** (first time only)
   ```bash
   npm install
   ```

2. **Start the development server**
   ```bash
   npm run dev
   ```

3. **Open in browser**
   Navigate to `http://localhost:5173`

## Build for Production

```bash
npm run build
npm run preview
```

## Project Features

### 🏠 Home Page
- Overview of Git's mental model
- Animated commit graph visualization
- Links to explore concepts and playground

### 📚 Concept Map (`/concepts`)
- Browse all Git concepts grouped by difficulty
- Search functionality to find specific topics
- Concepts organized into categories:
  - Git Fundamentals
  - Branches & HEAD
  - Merging & Rebasing
  - Undoing Changes
  - Remote Repositories
  - Advanced Git

### 📖 Concept Pages (`/concepts/:id`)
Each concept page includes:
- Clear definition
- Mental model explanation
- Command examples
- Animated visualizations
- Common mistakes to avoid

### 🎮 Playground (`/playground`)
Interactive Git operations:
- **Create Commits** - Add commits with custom messages
- **Branch Operations** - Create, delete, and checkout branches
- **Merge** - Fast-forward and three-way merges
- **Rebase** - Move commits to a new base
- **Reset** - Soft, mixed, and hard resets
- **Tag** - Create release tags
- **Undo/Redo** - Experiment without consequences

## Key Visualizations

### Commit Graph
- Commits shown as colored nodes
- Branches as labels on commits
- HEAD pointer (red triangle) showing current position
- Tags displayed as 🏷️ labels

### Inspector Panel
- Real-time view of:
  - HEAD position (branch or commit)
  - All branches and their commit references
  - Tags and their locations
  - Latest commit details
  - Repository statistics

## Theme Toggle
Click the sun/moon icon in the top-right to switch between:
- Light mode (default)
- Dark mode (saved to localStorage)

## Learning Path

1. **Start with Fundamentals** - Learn what Git is and how it works
2. **Explore Branches** - Understand branches as pointers
3. **Try Merging** - See fast-forward and three-way merges in action
4. **Experiment in Playground** - Create a real Git workflow safely
5. **Master Advanced Topics** - Cherry-pick, bisect, Git internals

## Keyboard Navigation
- Use standard browser navigation (Tab, Enter)
- Arrow keys for list navigation (where applicable)

## Accessibility
- Full keyboard support
- ARIA labels throughout
- Respects `prefers-reduced-motion` setting

## Tips

1. **Use Undo/Redo** in the playground to experiment freely
2. **Watch the commit graph** - it updates in real-time with each operation
3. **Check the Inspector** to understand what changed
4. **Read concept pages** before trying operations in the playground
5. **Start simple** - create a few commits, then try branching and merging

## Common Workflows to Try

### Feature Branch Workflow
1. Create initial commits on main
2. Create a feature branch
3. Make commits on feature branch
4. Merge feature back to main (fast-forward)
5. Repeat with multiple features

### Merge Conflict Scenario
1. Create two branches from the same commit
2. Make different changes on both branches
3. Try merging - see the three-way merge happen

### Rebase Experiment
1. Create main commits (A, B, C)
2. Create feature branch from A
3. Make feature commits (D, E)
4. Rebase feature onto main
5. Watch the linear history form

### Undo Experiment
1. Make several commits
2. Try different reset modes (soft, mixed, hard)
3. Use undo to recover

## Need Help?

- Check the main [README.md](./README.md) for detailed documentation
- Explore the concepts to understand Git's internal model
- Use the playground to safely experiment with Git operations

Enjoy learning Git visually! 🚀