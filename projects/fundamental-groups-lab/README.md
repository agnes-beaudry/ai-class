# Loop Lab

An interactive, dependency-free introduction to computing fundamental groups from gluing data. It turns standard polygon and graph gluings into group presentations and lets you highlight, trace, and reshape the generator loops.

## Run it

Open `index.html` directly in a browser, or serve the directory locally:

```bash
cd /workspaces/ai-sandbox/projects/fundamental-groups-lab
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

## Included examples

- Circle: `π₁(S¹) ≅ ℤ`
- Figure eight: `π₁(S¹ ∨ S¹) ≅ F₂`
- Torus: `⟨a,b | aba⁻¹b⁻¹ = 1⟩ ≅ ℤ²`
- Klein bottle: `⟨a,b | aba⁻¹ = b⁻¹⟩`
- Real projective plane: `⟨a | a² = 1⟩ ≅ ℤ/2ℤ`

## Mathematical scope

This first version teaches the one-vertex CW-complex method: each named 1-cell gives a generator, and each attached 2-cell contributes its boundary word as a relation. The pictures visualize the 1-skeleton and the selected generator; they are homotopy models, not literal drawings of each surface in 3D.
