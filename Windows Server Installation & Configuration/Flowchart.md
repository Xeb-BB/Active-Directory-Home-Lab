```mermaid
flowchart TD
    START([START]) --> A

    %% Phase 1
    subgraph P1 [Phase 1: Initial Server Configuration]
        A[1. Rename Hostname to SERVER] --> B[Reboot System]
        B --> C[2. Configure Static IP & Subnet]
        C --> D[Set Preferred DNS to 127.0.0.1]
        D --> E[3. Set Time Zone & Enable RDP]
        E --> F[4. Run Windows Update & Patch]
    end

    %% Connection between Phase 1 and Phase 2
    F -->|Baseline Complete| G

    %% Phase 2
    subgraph P2 [Phase 2: Role Installation & DC Promotion]
        G[1. Add Roles & Features Wizard] --> H[Check AD DS, DNS, & DHCP]
        H --> I[Execute Installation]
        I --> J[2. Click Notification Flag\nPromote to Domain Controller]
        J --> K[Select 'Add a new forest'\nSet Domain: css.com]
        K --> L[Set DSRM Password\n& Verify NetBIOS]
        L --> M[Pass Prerequisites Check\nClick Install]
    end

    %% Final Outcome
    M --> N([ System Auto-Reboots\nLog in as CSS\\Administrator])


