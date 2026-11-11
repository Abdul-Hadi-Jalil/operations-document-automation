# Architecture

The automation separates three adapters from one reporting boundary:

```mermaid
flowchart TB
    CFG[Environment configuration] --> A1[Ticket adapter]
    CFG --> A2[Drive adapter]
    CFG --> A3[Planning portal adapter]
    A1 --> N[Normalized operational records]
    A2 --> N
    A3 --> N
    N --> OUT[Controlled reporting destination]
```

Each adapter owns authentication, retrieval, and source-specific normalization. The reporting layer receives standardized records and file references rather than source-specific response structures.
