# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **algorithm problem-solving repository** for [Programmers](https://programmers.co.kr/), a Korean competitive programming platform similar to LeetCode. The project stores solutions to algorithm challenges organized by category and difficulty level.

### Directory Structure

- **`src/`** - Main source code directory containing placeholder/template files
  - `Solution.kt` - Kotlin template for solutions
  - `legacy/Solution.java` - Java template for solutions (legacy)
- **`cabinet/`** - Problem storage archive
  - Individual problem files organized by algorithm category (e.g., `[DFS|BFS][Level 2][Java]`, `[해시][Kotlin]`)
  - `secret/` - Additional problem solutions (including dev-matching and company-specific challenges)
- **`lib/`** - Kotlin standard library dependencies (kotlin-stdlib, kotlin-reflect, kotlin-test, etc.)
- **`out/`** - Build output directory

### Language & Environment

- **Languages**: Java (JDK 14) and Kotlin
- **IDE**: IntelliJ IDEA
- **Build System**: No explicit build tool (project is IDE-based)

## Development Setup

### Running Solutions

Since this is an IDE-based project without a build system:

1. **Java Solutions**: Open the file in IntelliJ and run directly
   - Main class: `legacy.Solution` (for .java files)
   - Right-click → Run or press `Ctrl+Shift+F10` (macOS: `Ctrl+Shift+R`)

2. **Kotlin Solutions**: Open the file in IntelliJ and run directly
   - Kotlin uses the companion object pattern with a `main` function
   - Right-click → Run or use IDE shortcuts

### Compiling

The project uses IntelliJ's built-in Kotlin and Java compilers. No command-line compilation is necessary for local development, but if needed:

```bash
# Java compilation (if required)
javac -d out src/legacy/Solution.java

# Kotlin compilation (if required - requires Kotlin compiler)
kotlinc src/Solution.kt -d out
```

## Problem Solution Format

Each problem solution file follows this pattern:

```
import statements...

/**
 * <h1>Problem Title in Korean</h1>
 * <h5>분류: Algorithm Category</h5>
 * <h5>난이도: Level X</h5>
 * <h5>풀이</h5>
 * <ul>
 * <li>Problem description and approach...</li>
 * </ul>
 */
public class Solution {
    public static void main(String[] args) {
        // Test cases
    }

    public static [returnType] solution([parameters]) {
        // Solution implementation
    }
}
```

### File Naming Convention

Problems are named with format: `[Algorithm Category][Level X][Language] 'Problem Title'.txt`

Examples:
- `[DFS|BFS][Level 2][Java] '게임 맵 최단거리'.txt`
- `[해시][Kotlin] '메뉴 리뉴얼'.txt`
- `[동적계획법][Level 3][Java] '등굣길'.txt`

## Algorithm Categories Covered

The repository includes solutions for the following algorithm topics:

- **DFS/BFS** (Depth-First Search / Breadth-First Search)
- **Hash** (해시)
- **Dynamic Programming** (동적계획법)
- **Stack/Queue** (스택|큐)
- **Complete Search** (완전탐색)
- **Sorting** (정렬)
- **Greedy** (탐욕)
- **Heap** (힙)
- **Monotonic Stack** (단조 스택)
- **Paper Folding** (종이접기)

## Common Development Tasks

### Adding a New Problem Solution

1. Create a new `.txt` file (or edit directly in `src/Solution.kt` or `src/legacy/Solution.java`)
2. Use the template format shown above
3. Include problem description and algorithm approach in JavaDoc comments
4. Implement the `solution()` method with the appropriate signature
5. Add test cases in the `main()` method
6. Name the file following the convention: `[Category][Level][Language] 'Problem Title'.txt`
7. Store in `cabinet/` directory (or `cabinet/secret/` for company-specific problems)

### Running a Single Problem

1. Copy the solution code to `src/Solution.kt` or `src/legacy/Solution.java`
2. Run directly from the IDE
3. The main method contains example test cases

### Testing

Most solutions include test cases directly in the `main()` method. To test:
- Run the file from the IDE
- Check console output for `System.out.println()` statements
- Verify results match expected outputs

## Notes for Future Development

- The project is **read-only storage** for problem solutions. Primary development workflow is within the IDE.
- Solutions use **inline testing** in the `main()` method rather than separate test files.
- The project includes solutions from **company hiring challenges** (e.g., Dev-Matching, CJ Olive Networks, Coinone) stored in `cabinet/secret/`.
- Kotlin solutions use `companion object` pattern to match Java's static main method convention.
