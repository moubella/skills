---
name: mermaid
description: Generate Mermaid diagrams (flowcharts, sequence, ER, class, state, gantt) from code or descriptions
allowed-tools: Read, Grep, Glob, Write, Bash
---

Generate a Mermaid diagram for: $ARGUMENTS

Rules:
- Choose the best diagram type for the request: flowchart (default), sequenceDiagram, classDiagram, erDiagram, stateDiagram-v2, gantt
- If $ARGUMENTS references a file, folder, or module, read the code first and diagram its architecture or flow
- Keep diagrams readable — max ~15 nodes per diagram, split into subgraphs if needed
- Use clear, short labels on nodes and edges
- Use direction TB (top-bottom) for flowcharts unless LR (left-right) fits better

Rendering:
1. Write the mermaid code to `/tmp/mermaid/chart.mmd` (create `/tmp/mermaid/` if needed)
2. Render locally with: `/opt/homebrew/bin/mmdc -i /tmp/mermaid/chart.mmd -o /tmp/mermaid/chart.svg -t dark -b transparent`
3. Open in browser with: `open /tmp/mermaid/chart.svg`
4. Overwrite the previous chart on each invocation
