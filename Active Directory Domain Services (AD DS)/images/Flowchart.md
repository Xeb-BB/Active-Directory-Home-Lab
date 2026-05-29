```mermaid 
flowchart TD
    START([ START]) --> A[Open Active Directory Users and Computers]

    %% OU Tree Structure
    subgraph OU_Setup [ 1. Organizational Unit Hierarchy]
        A --> B[Right-Click css.com Domain -> New -> OU]
        B --> C[Create Top-Level OU: 'Corporate'\nKeep Accidental Deletion Protected]
        C --> D[Create Nested Sub-OUs:]
        D --> D1[Departments]
        D --> D2[Groups]
        D --> D3[Users]
        D --> D4[Computers]
    end

    %% User Provisioning Flow
    subgraph Provisioning [ 2. User Onboarding Flow]
        D3 --> E[Right-Click 'Users' OU -> New -> User]
        E --> F[Input User Logons:\njbenriquez / jcenriquez]
        F --> G[Assign Temporary Complex Password]
        G --> H[Check box: 'User must change password at next logon']
    end

    %% Validation Loop
    subgraph Validation [ 3. Environment Validation]
        H --> I[Boot Domain-Joined Client Workstation]
        I --> J[Attempt Logon with New User Identity]
        J --> K{Authentication\nSuccessful?}
        K -->|Yes| L([ User Profile Created\nIAM Lab Verified])
        K -->|No| M[Troubleshoot Network Path / DNS Issues]
        M --> I
    end
