![](../w3c-no-bars.svg)

# SHACL UI Community Widget Registry

This directory is a **community-maintained registry** of [SHACL 1.2 UI](https://www.w3.org/TR/shacl12-ui/)
widgets, i.e., additional **viewers** and **editors** that extend the *built-in* widgets defined
normatively in the specification.

The registry exists so that new widgets can keep being added by the community **after** the W3C Data Shapes
Working Group charter has ended and the SHACL 1.2 UI specification has been locked. Because every widget is
defined entirely here, **no change to the specification is ever required to register a new widget.**


## Relationship to the specification

- The SHACL 1.2 UI specification defines a small set of **built-in widgets** in the `shui` namespace
  (`http://www.w3.org/ns/shacl-ui/`). That namespace is fixed once the specification is published.
- Community widgets registered here use the separate, **community-controlled** namespace
  `http://www.w3.org/ns/shacl-ui-community/` (suggested prefix `shuic`).
- Community widgets are ordinary instances of the specification's widget classes
  (`shui:Editor`, `shui:Viewer`, and their `shui:SingleEditor` / `shui:MultiEditor` /
  `shui:SingleViewer` / `shui:MultiViewer` refinements). The registry reuses those classes; it only mints
  new *widget* IRIs, never new `shui` terms.

See the specification's [Registries](https://www.w3.org/TR/shacl12-ui/#registries) section, which
references this registry.


## Contents

| **File / directory**    | **Content**                                                 |
|-------------------------|-------------------------------------------------------------|
| `README.md`             | This document.                                              |
| `CONTRIBUTING.md`       | How to add a community widget via a pull request.           |
| `registry.ttl`          | Machine-readable index (catalog) of the registered widgets. |
| `widgets/`              | One Turtle file per registered widget.                      |
| `widgets/_template.ttl` | Template to copy when adding a new widget.                  |

## Adding a widget

See [`CONTRIBUTING.md`](CONTRIBUTING.md). In short: copy `widgets/_template.ttl` to
`widgets/<WidgetName>.ttl`, fill it in, register it in `registry.ttl`, and open a pull request.
