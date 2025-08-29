Pyromancer, I love this “tree ⇒ forest” unification. You just got a one-file utility to make it real—copy/paste and go.

I dropped `forest.sh` in the canvas. It’s built around your ontology:

* tree = `{root, trunk, branching, canopy, fruit}`
* forest = many trees across `agent × space × time`
* safety = `.dt` marker (`ukb-<agent>_<space>_<time>.dt`) protects from reckless nukes
* pruning = your `find ... ! -name 'ukb-*.dt' -exec rm -rf {} +` vibe, but dry-run by default

### Quick start (copy/paste friendly)

```bash
chmod +x forest.sh

# 0) Initialize a forest
./forest.sh init ./FOREST

# 1) Grow a tree (agent × space × time)
./forest.sh grow --agent Ukuzula --space lab --time 2025Q3 --dir ./FOREST --note "mid-summer spark"

# 2) See what exists
./forest.sh list --dir ./FOREST
./forest.sh map  --dir ./FOREST --maxdepth 3

# 3) Prune safely (dry-run first, then --force)
./forest.sh prune --dir ./FOREST --maxdepth 2 --keep 'ukb-*.dt'
./forest.sh prune --dir ./FOREST --maxdepth 2 --keep 'ukb-*.dt' --force

# 4) Harvest artifacts from fruit/ (HTML, JPG, APP, etc.)
./forest.sh harvest --dir ./FOREST --ext ".html,.jpg,.app" --out ./HARVEST
```

### Why this matches your “same program at every scale”

* AST addressing (`agent/space/time`) = your agent × spatial × temporal indexing.
* Five folders per node = invariant ontology at every zoom level.
* Markers (`ukb-*.dt`) = digital-twin anchors; pruning respects them.
* `prune` and `harvest` are pure `find(1)` compositions—minimal, powerful, dangerous (but tamed).

Want me to add a `--clone` (copy a whole tree as a new time slice) or `--variant` (spawn theme variants under `fruit/variants/`)?
