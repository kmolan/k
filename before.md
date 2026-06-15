# IK solver robustness / accuracy benchmark

- Arm: `urdf/sample.urdf` `l_wrist_pitch` (6 DOF)
- Samples per set: 200
- Seed: `20240614`
- Residuals (meters / radians) are over successful solves only (`end_transform` vs target).

| Target set | Samples | Success | Rate | Panics | Non-finite | Pos mean | Pos max | Rot mean | Rot max |
|---|---|---|---|---|---|---|---|---|---|
| Well-conditioned | 200 | 200 | 100.0% | 0 | 0 | 7.08e-4 | 9.97e-4 | 2.19e-3 | 4.74e-3 |
| Near-singular | 200 | 18 | 9.0% | 0 | 0 | 6.86e-4 | 9.88e-4 | 1.23e-3 | 3.25e-3 |
| Redundant + limits | 200 | 199 | 99.5% | 0 | 0 | 6.94e-4 | 9.94e-4 | 9.10e-2 | 1.02e0 |
