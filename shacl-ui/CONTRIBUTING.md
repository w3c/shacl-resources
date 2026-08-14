# Contributing a widget to the SHACL UI Community Widget Registry

This registry holds community-maintained [SHACL 1.2 UI](https://www.w3.org/TR/shacl12-ui/) widgets
(viewers and editors) that extend the built-in widgets defined in the specification.

**No change to the SHACL 1.2 UI specification is required to add a widget.** Everything lives in this
repository, which remains editable after the Working Group charter ends.

## Prerequisites

- Your widget must be an instance of one of the specification's widget classes:
  - Editors: `shui:Editor`, refined as `shui:SingleEditor` or `shui:MultiEditor`.
  - Viewers: `shui:Viewer`, refined as `shui:SingleViewer` or `shui:MultiViewer`.
- Give it an IRI in the community namespace
  `http://www.w3.org/ns/shacl-ui-community/` (prefix `shuic`), e.g. `shuic:MarkdownViewer`.
  Do **not** mint IRIs in the `shui` namespace (`http://www.w3.org/ns/shacl-ui/`) — that namespace is
  locked by the published specification.

## Steps

1. **Copy the template.**
   ```
   cp widgets/_template.ttl widgets/<WidgetName>.ttl
   ```
   For example `widgets/MarkdownViewer.ttl`.

2. **Fill it in.** Set the widget IRI, its type(s), `rdfs:label`, `rdfs:comment`,
   attribution (`dcterms:creator`), and any `rdfs:seeAlso` documentation links.
   If the widget should be selected automatically, add one or more `shui:WidgetScore` instances (with
   `shui:widget`, `shui:score`, and `shui:dataGraphShape` / `shui:shapesGraphShape`) and the matcher
   shapes they reference — the same structure the built-in widgets use. See the specification's
   "Scoring System" and "Built-in Widgets" sections.

3. **Register it in `registry.ttl`.** Add two lines to the `shuic:widgetRegistry` resource:
   ```turtle
   shuic:widgetRegistry
       # ...
       owl:imports <widgets/<WidgetName>.ttl> ;
       shuic:hasWidget shuic:<WidgetName> ;
   .
   ```

4. **Validate.** Ensure both `registry.ttl` and your widget file parse as Turtle. If your widget
   defines `shui:WidgetScore` instances, continuous integration validates them against the
   specification's Widget Score validator; you can run the same check locally with
   [`pyshacl`](https://github.com/RDFLib/pySHACL):
   ```
   curl -fsSL https://raw.githubusercontent.com/w3c/data-shapes/gh-pages/shacl12-ui/widgets/score-validator.ttl -o score-validator.ttl
   pyshacl -s score-validator.ttl widgets/<WidgetName>.ttl
   ```

5. **Open a pull request** against `w3c/shacl-resources`. Describe the widget.

## Guidelines

- Keep one widget per file under `widgets/`.
- Prefer clear, specific `rdfs:label` and `rdfs:comment` values so the widget is discoverable.
- If your widget targets a particular datatype or value kind, say so explicitly in the description.
- Widgets that need the scoring system to select them automatically should include a scoring definition;
  see the specification's "Scoring System" section.
