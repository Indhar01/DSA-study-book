# DSA eBook for AI Engineer Roles — Plan

## Top-Level Overview

**Goal:** Generate a single, self-contained `dsa-ebook.html` file — a professionally styled, interactive DSA study book tailored for AI Engineer candidates at product-based companies.

**Format:** Single HTML file with:
- Embedded CSS (light/dark toggle, syntax highlighting, sidebar TOC)
- All content and code inline — no external dependencies except Google Fonts CDN
- Chapters organized exactly as specified in the user's 15-section outline
- Every problem follows the 9-cell pattern: Concept → Visual → Template → Problem → Critical Thinking → Implementation → Test Cases → Complexity → Interview Tips

**Scope:** 15 sections, ~75 problems/concepts, all code in Python 3 with type hints.

**Non-goals:**
- No backend, no server, no build step
- No JavaScript frameworks (vanilla JS only for TOC toggle + dark mode)
- No external CSS libraries

---

## Sub-Tasks

### Sub-Task 1 — HTML Shell, Design System, and Navigation

**Intent:** Build the complete HTML skeleton with CSS variables, light/dark theme, sidebar TOC, and responsive layout. This shell is the container that all content slots into.

**Expected Outcomes:**
- A valid `.html` file with full `<head>`, `<body>`, sidebar, content pane, and dark mode toggle
- CSS custom properties for both themes (colors, fonts, spacing)
- Sticky sidebar with anchor-linked TOC that collapses on mobile
- Syntax-highlighted `<pre><code>` blocks styled via embedded CSS (Prism-style, no CDN)
- Light/dark toggle button that persists via localStorage

**Todo List:**
1. Define color palette: light mode (white bg, slate text, blue accent) and dark mode (gray-900 bg, gray-100 text, cyan accent)
2. Set up CSS custom properties (`--bg`, `--surface`, `--text`, `--accent`, `--code-bg`, etc.)
3. Write responsive two-column layout: fixed sidebar (260px) + scrollable main content
4. Build TOC sidebar HTML with anchor links for all 15 sections and their sub-problems
5. Write the dark mode toggle button + vanilla JS (3 lines: toggle class, save to localStorage, restore on load)
6. Style code blocks with embedded token-coloring CSS (keywords, strings, comments, numbers in distinct colors)
7. Style markdown-equivalent elements: `h1–h4`, `p`, `ul/ol`, `table`, `blockquote`, `badge`
8. Add "Section Summary" card style and "Confidence Tracker" table style
9. Add print-friendly `@media print` CSS
10. Validate the shell renders correctly with placeholder content

**Relevant Context:** UI skill rules: dark-mode pairing, contrast ≥4.5:1, font-scale, spacing-scale, mobile-first, z-index-management

**Status:** [ ] pending

---

### Sub-Task 2 — Section 1 & 2: Foundations + Arrays & Strings

**Intent:** Write full content for Sections 1 and 2 following the 9-cell pattern for every concept and problem.

**Expected Outcomes:**
- Section 1: Big O Notation, Recursion, Problem-Breakdown framework — each with ASCII diagrams and worked examples
- Section 2: Two Pointers, Sliding Window, Prefix Sum, Kadane's, Matrix Traversal + all 7 listed problems
- All Python code uses type hints, inline comments, passes test cases
- Section Summary cell at end of each section

**Todo List:**
1. Write Section 1 — Big O: concept, O(1)/O(n)/O(n²)/O(log n) ASCII table, comparison template, complexity analysis cell
2. Write Section 1 — Recursion: concept, recursion tree ASCII diagram, base-case/recursive-case template, Fibonacci example with memoization
3. Write Section 1 — Problem Breakdown: UMPIRE preview, brute-force-to-optimized thinking framework
4. Write Section 2 — Two Pointers: concept, visual, template, then problems: Longest Substring (placeholder — moved to sliding window)
5. Write Section 2 — Sliding Window: concept, visual, template, then: Longest Substring Without Repeating Characters, Minimum Window Substring
6. Write Section 2 — Prefix Sum: concept, visual, template
7. Write Section 2 — Kadane's Algorithm: concept, visual, template, then: Maximum Subarray
8. Write Section 2 — Matrix Traversal: concept, ASCII grid, template, then: Rotate Image, Spiral Matrix
9. Write problem: Best Time to Buy and Sell Stock (two pointers / single pass)
10. Write problem: Product of Array Except Self (prefix/suffix product)
11. Add Section Summary cells

**Relevant Context:** Sub-Task 1 must be complete — all content goes inside the HTML shell's main content area.

**Status:** [ ] pending

---

### Sub-Task 3 — Sections 3, 4, 5: Hashing + Linked Lists + Stacks & Queues

**Intent:** Write full 9-cell content for all three sections and their problems.

**Expected Outcomes:**
- Section 3 (Hashing): HashMap/HashSet patterns, frequency counting, 5 problems
- Section 4 (Linked Lists): Singly + Doubly implementation, fast/slow pointer, 5 problems
- Section 5 (Stacks & Queues): Monotonic stack pattern, 5 problems
- All code executable with no imports beyond `collections`, `heapq`, `functools`, `itertools`

**Todo List:**
1. Section 3 — HashMap/HashSet: concept, ASCII bucket diagram, frequency template
2. Section 3 problems: Two Sum, Group Anagrams, Top K Frequent Elements, Valid Anagram, Longest Consecutive Sequence
3. Section 4 — LinkedList class implementation (Node + singly LL with visual pointer ASCII)
4. Section 4 — Fast/Slow Pointer: concept + visual
5. Section 4 problems: Reverse Linked List, Merge Two Sorted Lists, Linked List Cycle, Reorder List, Remove Nth Node From End
6. Section 5 — Stack/Queue: concept, monotonic stack visual (ascending/descending)
7. Section 5 problems: Valid Parentheses, Min Stack, Daily Temperatures, Largest Rectangle in Histogram, Sliding Window Maximum
8. Add Section Summary cells for all three sections

**Relevant Context:** Reuse LinkedList Node class across Section 4 problems. Monotonic stack template reused across Section 5 problems.

**Status:** [ ] pending

---

### Sub-Task 4 — Sections 6, 7, 8: Binary Search + Trees + Heaps

**Intent:** Write full 9-cell content for binary search, tree traversals, BST, and heap patterns.

**Expected Outcomes:**
- Section 6 (Binary Search): classic template, search-on-answer-space pattern, 5 problems
- Section 7 (Trees): DFS/BFS/Inorder/Preorder/Postorder, BST, 8 problems
- Section 8 (Heaps): min-heap/max-heap via `heapq`, 4 problems
- ASCII diagrams for tree structures, heap visualization

**Todo List:**
1. Section 6 — Binary Search: concept, `lo/hi/mid` ASCII, 3-template variants (exact / left-bound / right-bound)
2. Section 6 — Search on answer space concept + template
3. Section 6 problems: Binary Search, Search in Rotated Sorted Array, Find Minimum in Rotated Sorted Array, Median of Two Sorted Arrays, Koko Eating Bananas
4. Section 7 — TreeNode class + all traversal implementations (iterative + recursive)
5. Section 7 — BFS (level order) with queue visual
6. Section 7 — BST insert/search/delete
7. Section 7 problems: Max Depth, Same Tree, Invert Binary Tree, Level Order Traversal, Validate BST, LCA, Serialize/Deserialize, Max Path Sum
8. Section 8 — heapq API cheat sheet, min-heap/max-heap (negate trick) visual
9. Section 8 problems: Kth Largest Element, Merge K Sorted Lists, Task Scheduler, Find Median from Data Stream
10. Add Section Summary cells

**Relevant Context:** TreeNode class defined once at start of Section 7, reused in all tree problems.

**Status:** [ ] pending

---

### Sub-Task 5 — Sections 9 & 10: Graphs + Dynamic Programming

**Intent:** Write full content for graphs (the most complex section) and the full DP section with pattern taxonomy.

**Expected Outcomes:**
- Section 9 (Graphs): adjacency list + matrix, DFS/BFS, Union-Find, Topological Sort, 6 problems
- Section 10 (DP): 1D/2D/Knapsack/Subsequence/Interval DP patterns, how-to-identify framework, 10 problems
- Union-Find class implementation reused across graph problems
- DP "identify the pattern" decision tree in ASCII

**Todo List:**
1. Section 9 — Graph representations: adjacency list vs matrix ASCII comparison table
2. Section 9 — DFS template (iterative + recursive), BFS template
3. Section 9 — Union-Find class with union-by-rank + path compression
4. Section 9 — Topological Sort (BFS Kahn's + DFS approaches)
5. Section 9 problems: Number of Islands, Clone Graph, Pacific Atlantic Water Flow, Course Schedule, Number of Connected Components, Word Ladder
6. Section 10 — DP pattern identification framework (overlapping subproblems + optimal substructure check)
7. Section 10 — 1D DP, 2D DP, Knapsack, Subsequence, Interval DP templates
8. Section 10 problems: Climbing Stairs, House Robber, LCS, Edit Distance, Coin Change, Word Break, Unique Paths, Jump Game, Partition Equal Subset Sum, LIS
9. Add Section Summary cells

**Relevant Context:** Graph section is the largest — graph class and Union-Find class defined once at the top of Section 9.

**Status:** [ ] pending

---

### Sub-Task 6 — Sections 11–14: Backtracking + Greedy + Tries + Advanced

**Intent:** Write full content for backtracking, greedy, tries, and AI-Engineer-specific advanced topics.

**Expected Outcomes:**
- Section 11 (Backtracking): universal template, 6 problems
- Section 12 (Greedy): when-to-apply framework, 5 problems
- Section 13 (Tries): full Trie class implementation, 3 problems
- Section 14 (Advanced): bit manipulation, math/number theory, randomized algorithms, 3 AI-specific problems
- All code self-contained and executable

**Todo List:**
1. Section 11 — Backtracking template (choose/explore/unchoose pattern) with visual decision tree
2. Section 11 problems: Subsets, Permutations, Combination Sum, N-Queens, Word Search, Palindrome Partitioning
3. Section 12 — Greedy: when-to-apply checklist (exchange argument, greedy choice property)
4. Section 12 problems: Jump Game II, Gas Station, Meeting Rooms, Merge Intervals, Non-overlapping Intervals
5. Section 13 — Trie class (TrieNode + Trie with insert/search/startsWith)
6. Section 13 problems: Implement Trie (already done by class), Word Search II, Design Add and Search Words
7. Section 14 — Bit Manipulation: AND/OR/XOR/shift operations table, common patterns (check bit, set bit, clear bit, count bits)
8. Section 14 — Math: GCD (Euclidean), prime sieve, modular arithmetic
9. Section 14 — Reservoir Sampling + Fisher-Yates Shuffle
10. Section 14 problems: Random Pick with Weight, Shuffle an Array, Find K Closest Points to Origin
11. Add Section Summary cells

**Relevant Context:** Section 13 Trie class is also the solution to the first problem — structure accordingly.

**Status:** [ ] pending

---

### Sub-Task 7 — Section 15: Interview Strategy + Confidence Tracker + Final Assembly

**Intent:** Write Section 15 (interview meta-strategy), add the Confidence Tracker table, wire up all sections into the final HTML, and validate the complete file.

**Expected Outcomes:**
- Section 15: UMPIRE method walkthrough, complexity communication guide, common mistakes, 6-week study plan table
- Confidence Tracker: one table row per topic with self-rating columns (1–5, ✓/✗, Notes)
- Complete `dsa-ebook.html` with all 15 sections assembled
- TOC sidebar anchor links verified
- Dark/light toggle working
- All code blocks correctly highlighted
- File is self-contained (no broken external links)

**Todo List:**
1. Write Section 15 — UMPIRE method with worked example walkthrough
2. Write Section 15 — How to communicate complexity to an interviewer (script format)
3. Write Section 15 — Common mistakes table (mistake → what interviewer sees → how to fix)
4. Write Section 15 — 6-week study plan as a structured HTML table
5. Write Confidence Tracker table (all 15 topics + sub-topics, rating columns)
6. Assemble all sub-task content into the final single HTML file (Sub-Tasks 1–6 outputs merged)
7. Verify all TOC anchor `href` values match section `id` attributes
8. Verify dark mode toggle applies to code blocks, tables, and sidebar
9. Verify all Python code blocks are syntactically correct (manual review)
10. Write final file as `dsa-ebook.html`

**Relevant Context:** This is the integration sub-task — all previous sub-tasks feed into here. The HTML shell from Sub-Task 1 is the wrapper.

**Status:** [ ] pending

---

## Notebook Content Rules (apply to all sub-tasks)

- Every problem follows the 9-cell pattern: Concept → Visual → Template → Problem Statement → Critical Thinking → Implementation → Test Cases → Complexity Analysis → Interview Tips
- All Python code: Python 3, type hints on all functions, inline comments on non-obvious lines
- Tone: mentor guiding a student — conversational but technically precise
- Imports allowed: `collections`, `heapq`, `functools`, `itertools`, `typing`, `math`, `random` only
- Every section ends with a Section Summary listing patterns learned and problems solved
- ASCII diagrams must be inside `<pre>` blocks with monospace font class

## Design System (applied in Sub-Task 1)

- **Style:** Minimalist technical documentation with developer aesthetic
- **Light palette:** background `#f8fafc`, surface `#ffffff`, text `#1e293b`, accent `#2563eb`, code-bg `#f1f5f9`
- **Dark palette:** background `#0f172a`, surface `#1e293b`, text `#e2e8f0`, accent `#38bdf8`, code-bg `#020617`
- **Font:** Inter (body) + JetBrains Mono (code) via Google Fonts CDN
- **Syntax tokens (dark):** keywords `#c792ea`, strings `#c3e88d`, comments `#546e7a`, numbers `#f78c6c`, functions `#82aaff`
- **Syntax tokens (light):** keywords `#7c3aed`, strings `#16a34a`, comments `#94a3b8`, numbers `#ea580c`, functions `#2563eb`
- **Spacing:** 8px base unit, section padding 48px, code block padding 20px
- **Border radius:** cards 12px, code blocks 8px, badges 4px
