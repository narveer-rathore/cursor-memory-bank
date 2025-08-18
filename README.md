# Cursor - Memory Bank System

## tldr;
- Clone / Copy rules directory to your project
- Type "initialize memory bank" in chat with agent
- other commands "update memory bank"

## The Problem: AI Memory Loss

### What Happens Without Memory Bank?

Every time you start a new AI session, the AI assistant begins with **zero knowledge** about your project. This creates significant problems:

#### **Repetitive Context Setting**
- Spend 10-15 minutes explaining project structure every session
- Repeatedly describe coding standards and preferences
- Re-explain architectural decisions and patterns
- Constantly clarify component relationships and dependencies

#### **Inconsistent Code Quality**
- AI suggests different patterns each session
- Inconsistent naming conventions across components
- Varying approaches to similar problems
- No awareness of established project standards

#### **Lost Project Knowledge**
- Previous architectural decisions forgotten
- No understanding of what's been tried and failed
- Unaware of current project priorities and focus areas
- Cannot reference past implementations or patterns

#### **Increased Technical Debt**
- Inconsistent code patterns create maintenance burden
- Mixed architectural approaches reduce code clarity
- Duplicated solutions for similar problems
- Harder to onboard new team members

### Real-World Impact

**Before Memory Bank:**
```
Session 1: "Create a React component"
AI: "I'll create a class component with styled-components"

Session 2: "Create another component" 
AI: "I'll create a functional component with CSS-in-JS"

Session 3: "Review my code"
AI: "I see mixed patterns. What's your preferred approach?"
```

**After Memory Bank:**
```
Every Session: AI reads memory bank and knows:
- Use functional components with TypeScript
- CSS Modules for styling
- Specific project patterns and standards
```

## The Solution: Memory Bank System

The Memory Bank System solves these problems by creating a **persistent knowledge base** that:

### **Maintains Context Across Sessions**
- AI remembers project structure and goals
- Consistent coding standards applied every time
- Architectural decisions preserved and referenced
- Current priorities and focus areas maintained

### **Preserves Project Knowledge**
- What's been built and what's left to do
- Successful patterns and approaches
- Failed attempts and lessons learned
- Evolution of project decisions over time

### **Accelerates Development**
- Zero time spent re-explaining project context
- Immediate productive AI assistance
- Consistent patterns reduce decision fatigue
- Faster onboarding for new team members

### **Ensures Quality**
- Consistent coding standards enforcement
- Architectural pattern compliance
- Built-in accessibility and performance standards
- Automated code review against established patterns









## Memory Bank vs Rules Comparison

| Aspect | Memory Bank Files (`memory-bank/`) | Rules Files (`.cursor/rules/`) |
|--------|-----------------------------------|--------------------------------|
| **Purpose** | Comprehensive project knowledge and context | Immediate coding standards and preferences |
| **Scope** | Project-wide understanding and historical context | Code implementation and formatting standards |
| **Content** | Architecture, decisions, progress, patterns | Syntax rules, naming conventions, tool preferences |
| **Usage** | Read by AI at session start for full context | Applied during active coding sessions |
| **Maintenance** | Updated after major changes or milestones | Updated when coding standards change |
| **Files** | 00-05 numbered files + rules.md | core.mdc, memory-bank.mdc, coding-standards.mdc |
| **Focus** | What to build and why | How to build it |
| **Frequency** | Updated periodically | Referenced continuously |

### How They Work Together

```
┌─────────────────┐    ┌─────────────────┐
│   Memory Bank   │    │     Rules       │
│   (Context)     │    │   (Standards)   │
│                 │    │                 │
│ • Project Goals │    │ • Code Style    │
│ • Architecture  │    │ • Naming        │
│ • Decisions     │    │ • Formatting    │
│ • Progress      │    │ • Tools         │
└─────────────────┘    └─────────────────┘
         │                       │
         └───────────┬───────────┘
                     │
            ┌─────────────────┐
            │   AI Assistant  │
            │                 │
            │ • Full Context  │
            │ • Code Standards│
            │ • Consistent    │
            │   Development   │
            └─────────────────┘
```

## File Structure Documentation

### Core Memory Bank Files

Our system consists of 7 core files in the `memory-bank/` directory:

1. **`00-project-context.md`** - Foundation document (project overview, goals, scope)
2. **`01-product-context.md`** - Product goals and user experience objectives  
3. **`02-system-patterns.md`** - System architecture and design patterns
4. **`03-tech-context.md`** - Technologies, tools, and technical constraints
5. **`04-active-context.md`** - Current work focus and recent decisions
6. **`05-progress-log.md`** - Progress tracking and status updates
7. **`rules.md`** - Implementation patterns and team preferences

### File Hierarchy and Dependencies

```
00-project-context.md (Foundation)
├── 01-product-context.md
├── 02-system-patterns.md  
├── 03-tech-context.md
└── 04-active-context.md ← (depends on 01, 02, 03)
    ├── 05-progress-log.md
    └── rules.md
```

**Dependency Flow:**
- Files 01, 02, 03 depend on 00 (foundation)
- File 04 depends on files 01, 02, and 03 combined
- Files 05 and rules.md depend on file 04

### Rules Files Structure

Located in `.cursor/rules/`:
- **`core.mdc`** - Core development rules and standards
- **`memory-bank.mdc`** - Memory bank system rules
- **`coding-standards.mdc`** - Comprehensive coding standards for both development and code review

## Coding Standards Integration

1. Follow `.cursor/rules/coding-standards.mdc` guidelines
2. Apply patterns from `memory-bank/rules.md`
3. Ensure accessibility compliance
4. Use proper TypeScript typing
5. Implement performance best practices
6. Follow naming conventions

### Using coding-standards.mdc for Development and Code Review

The `coding-standards.mdc` file serves as the **single source of truth** for all coding standards in the project. It serves two primary purposes:

1. **Development Guidelines** - Standards for daily development, refactoring, and component structure
2. **Code Review Standards** - Criteria for AI-assisted and human code reviews

**Note:** When requesting code reviews, you can also reference Git context (commits, branches, pull requests) to provide additional context about the changes being reviewed.

### Development Usage

#### For Daily Development
```
Please help me implement this feature following the coding standards in .cursor/rules/coding-standards.mdc:

[Describe feature requirements]
```

#### For Code Refactoring
```
Please refactor this code to align with our coding standards in .cursor/rules/coding-standards.mdc:

[Include code to be refactored]
```

### Code Review Usage

#### Step 1: Prepare Code Review Request
```
Please review this code using the coding standards in `.cursor/rules/coding-standards.mdc`:

[Include code to be reviewed]
```

#### Step 2: AI Review Process
The AI will automatically:
1. Read the `.cursor/rules/coding-standards.mdc` file
2. Compare code against established standards
3. Check for consistency with memory bank patterns
4. Provide specific feedback and recommendations

#### Step 3: Review Categories
The AI will review for:
- **Code Style**: Formatting, naming conventions, structure
- **TypeScript**: Type safety, interface definitions
- **React Patterns**: Component structure, hooks usage
- **Accessibility**: ARIA attributes, semantic HTML
- **Performance**: Optimization opportunities
- **Architecture**: Consistency with established patterns

#### Sample AI Development Prompt
```
Please help me create a new React component following our coding standards:

Component requirements: [Describe component needs]
```

#### Sample AI Code Review Prompt
```
Please conduct a comprehensive code review of this React component using our established coding standards:

[Include component code here]
```
