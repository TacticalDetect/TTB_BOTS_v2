# **"Can't Hide in 3D"** 
<p align="center">
  <img src="https://github.com/TacticalDetect/TTB_BOTS_v2/blob/main/spl_query/ttb.gif" alt="TTB 3D Visualization" width="700">
</p>

## Practical Implementation of Time-Terrain-Behavior Framework

In a sea of millions of security events, one workstation literally stood out, floating high above all the others when I transformed flat logs into a 3D visualization. I wasn't hunting for it. I didn't filter for it. It emerged naturally.

This repository contains the complete SPL implementation that identified Amber's workstation as a behavioral outlier in the Splunk BOTS v2 dataset, as featured in [THOR Collective Dispatch](https://dispatch.thorcollective.com/p/cant-hide-in-3d), and recognized in Detection Engineering Weekly's "[State of the Art](https://www.detectionengineering.net/i/173006335/state-of-the-art)" section (Issue #128).

### The Core Finding
Every SOC faces the same paradox: drowning in millions of events while blind to the patterns within them. This implementation proves that unusual behavior patterns **can't hide in 3D space** when you measure diversity across Time, Terrain, and Behavior dimensions.

## What This Implementation Achieves

- **Operationalizes MITRE's TTB framework** with working SPL code
- **Transforms categorical concepts** into measurable 3D coordinates  
- **Validates detection without prior knowledge** - no IOCs, no rules
- **Finds Amber's workstation** without targeting it, without filtering for it

## The Results That Matter

```
Amber's Workstation vs Normal Workstations:
├── Terrain: 11 security tool categories (vs 3-5 normal)
├── Time: 10 distinct contexts (vs 4-6 normal)
└── Behavior: 13+ action types (vs 4-7 normal)
```

## Repository Contents

```
/TTB_BOTS_v2
├── /spl_query
│   └── full_implementation.spl
```

## Quick Implementation

1. Load BOTS v2 dataset into Splunk
2. Install 3D Scatterplot from Splunkbase
3. Run `full_implementation.spl`
4. Watch Amber's workstation emerge as the outlier

## The No-Cheating Methodology

For TTB to be useful in real environments, it must detect unusual behavior without prior knowledge of what to look for. My testing approach:

- Analyzed the whole 30-day time period
- Included multiple data sources across the environment
- Didn't filter for known indicators of compromise
- Created generic behavioral categories
- Let clustering happen naturally in 3D space

## Why This Works

Traditional detection looks for known bad: specific artifacts, IOCs, correlation rules. But what about the unknown unknowns?

In the BOTS v2 scenario, the attacker:
- Used legitimate credentials
- Performed actions that individually looked normal
- Blended with regular traffic
- Still compromised the entire environment

No single rule would catch this. But the attacker's overall pattern was completely abnormal. The 3D visualization made it impossible to miss.

## Technical Foundation

### The TTB Model
- **X-axis (Terrain)**: How many different security tools observe activity
- **Y-axis (Time)**: When workstations are active
- **Z-axis (Behavior)**: Diversity of actions performed

### The Critical Transformation
```
MITRE Categories → Numerical Metrics → 3D Space
     ↓                    ↓                ↓
"Morning/Evening"    Count Distinct    Y coordinate
"Network/Endpoint"   Count Distinct    X coordinate  
"Login/Execute"      Count Distinct    Z coordinate
```

## Implementation Requirements

- Splunk Enterprise 8.x+
- 3D Scatterplot Visualization
- BOTS v2 dataset
- ~5 minutes runtime

## Citation

```
Certis Foster, "Can't Hide in 3D: Practical Implementation of TTB Framework", 
THOR Collective Dispatch, 9/4/25. GitHub: github.com/TacticalDetect/TTB_BOTS_v2
```

## Author

**Certis Foster**
- Featured in: [THOR Collective Dispatch](https://dispatch.thorcollective.com/p/cant-hide-in-3d)
- Featured in: Detection Engineering Weekly's "[State of the Art](https://www.detectionengineering.net/i/173006335/state-of-the-art)" section (Issue #128).
- LinkedIn: https://www.linkedin.com/in/certisf/
- Substack: https://tacticaldetect.substack.com/

## License

MIT License - Use freely, attribute appropriately.

## Acknowledgments

- MITRE for TTB framework theory
- Splunk for BOTS v2 dataset  
- THOR Collective Dispatch for publication platform

---
