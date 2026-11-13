# Token Generator
Create semantic reusable tokens; priority: Semantic tokens → component aliases → primitives.
Use only needed categories: color, typography, spacing, size, radius, border, shadow, motion, z-index.
Prefer semantic names. Components should not consume raw primitives when semantic roles exist.
Use compact typography roles and a predictable spacing scale (e.g. 4/8/12/16/20/24/32/40/48) adapted to the product. Keep radius/elevation restrained; standard cards often need no shadow.
Existing project: audit, map duplicates, preserve naming conventions, avoid full rename unless requested.
Reference-derived: extract repeated values, group by semantic role, remove near-duplicates, normalize spacing/radius, add needed states, preserve brand. Do not tokenise every pixel.
Once tokens exist, components consume them; true one-offs require a reason.
