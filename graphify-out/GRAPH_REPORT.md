# Graph Report - mungkas-desk  (2026-11-14)

## Corpus Check
- 13 files · ~14,983 words
- Verdict: corpus is large enough that graph structure adds value.
- Unclassified: 3 file(s) not represented in the graph (top: (none) 1, .example 1, .jsonc 1)

## Summary
- 106 nodes · 126 edges · 9 communities (8 shown, 1 thin omitted)
- Extraction: 91% EXTRACTED · 9% INFERRED · 0% AMBIGUOUS · INFERRED: 11 edges (avg confidence: 0.85)
- Token cost: 0 input · 0 output

## Graph Freshness
- Built from commit: `9eef3989`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- database.go
- steps
- handlers_users.go
- model.go
- package.json
- mungkasdesk/backend
- ci.yml
- helpers.js
- run.js

## God Nodes (most connected - your core abstractions)
1. `steps` - 5 edges
2. `build` - 4 edges
3. `createUser()` - 4 edges
4. `parseUserID()` - 4 edges
5. `scripts` - 4 edges
6. `on` - 3 edges
7. `with` - 3 edges
8. `getUserByID()` - 3 edges
9. `updateUser()` - 3 edges
10. `playwright` - 3 edges

## Surprising Connections (you probably didn't know these)
- `main()` --calls--> `connectDB()`  [INFERRED]
  backend/cmd/api/main.go → backend/cmd/api/database.go
- `getUserByID()` --calls--> `parseUserID()`  [INFERRED]
  backend/cmd/api/handlers_users.go → backend/cmd/api/validate.go
- `updateUser()` --calls--> `parseUserID()`  [INFERRED]
  backend/cmd/api/handlers_users.go → backend/cmd/api/validate.go
- `createUser()` --calls--> `containsSymbol()`  [INFERRED]
  backend/cmd/api/handlers_users.go → backend/cmd/api/validate.go
- `createUser()` --calls--> `containsUpper()`  [INFERRED]
  backend/cmd/api/handlers_users.go → backend/cmd/api/validate.go

## Import Cycles
- None detected.

## Communities (9 total, 1 thin omitted)

### Community 0 - "database.go"
Cohesion: 0.22
Nodes (3): connectDB(), getHealth(), main()

### Community 1 - "steps"
Cohesion: 0.17
Nodes (12): defaults, runs-on, steps, run, build, working-directory, name, run (+4 more)

### Community 2 - "handlers_users.go"
Cohesion: 0.14
Nodes (8): login(), createUser(), getUserByID(), getUsers(), updateUser(), containsSymbol(), containsUpper(), parseUserID()

### Community 3 - "model.go"
Cohesion: 0.29
Nodes (4): CreateUserInput, LoginInput, UpdateUserInput, User

### Community 4 - "package.json"
Cohesion: 0.12
Nodes (16): author, dependencies, playwright@^1.62.0, description, engines, node, keywords, license (+8 more)

### Community 6 - "ci.yml"
Cohesion: 0.22
Nodes (8): jobs, name, on, pull_request, push, permissions, contents, branches

### Community 8 - "helpers.js"
Cohesion: 0.15
Nodes (7): { chromium, firefox, webkit }, createContext(), fs, getExtraHeadersFromEnv(), http, os, path

### Community 9 - "run.js"
Cohesion: 0.17
Nodes (5): args, fs, nodeModules, path, { spawn }

## Knowledge Gaps
- **1 isolated node(s):** `mungkasdesk/backend`
  These have ≤1 connection - possible missing edges. (Counts symbols only; 55 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `playwright` connect `package.json` to `helpers.js`?**
  _High betweenness centrality (0.077) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `createUser()` (e.g. with `containsSymbol()` and `containsUpper()`) actually correct?**
  _`createUser()` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `mungkasdesk/backend` to the rest of the system?**
  _1 weakly-connected nodes found - possible missing edges._
- **Should `handlers_users.go` be split into smaller, more focused modules?**
  _Cohesion score 0.14492753623188406 - nodes in this community are weakly interconnected._
- **Why does `build` connect `steps` to `ci.yml`?**
  _High betweenness centrality (0.024) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `parseUserID()` (e.g. with `getUserByID()` and `updateUser()`) actually correct?**
  _`parseUserID()` has 2 INFERRED edges - model-reasoned connections that need verification._
- **Should `package.json` be split into smaller, more focused modules?**
  _Cohesion score 0.125 - nodes in this community are weakly interconnected._