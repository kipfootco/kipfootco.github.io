# Kipfoot Engineering Tool UI Kit

## Overview
The individual tool screen. Dense but clean: left input panel, right results panel, interactive diagram below. Nicky Case-style expandable explanations inline.

## Screens
1. **Tool Header** — Breadcrumb, tool name, discipline tag, actions
2. **Input Panel** — Grouped form fields with labels and units
3. **Results Panel** — KPI cards, utilization bars, status badges
4. **Diagram Area** — Interactive SVG diagram (bay, section, load envelope)
5. **Expandable Explanations** — Learn more, equation trace, assumptions

## Components
- `ToolHeader` — name, tag, run button, export button
- `InputGroup` — labeled section of related inputs
- `InputField` — label + input + unit suffix + helper
- `ResultsPanel` — grid of KPI cards
- `KPICard` — value, unit, delta, utilization bar
- `DiagramPanel` — SVG wrapper with controls
- `ExpandablePanel` — learn/equation/assumption accordion
