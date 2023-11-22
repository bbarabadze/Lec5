# Social Network

This program operates on a social network's data comprised of 4 CSV files, each containing specific tables:

- **Friends table**: Contains information about friendships.
- **Posts table**: Contains information about users' posting activities.
- **Reactions table**: Contains information about user reactions.
- **Users table**: Contains personal data about users.

The program performs several tasks:
- Checks the existence of data files.
- Partitions reactions and posts files based on post or reaction type.
- Verifies data consistency between original and partitioned files.
- Analyzes data and:
  - Prints a list of the top 10 most common names on the social network.
  - Prints a list of the top 5 most active users on the social network.


```mermaid
flowchart LR;
    S(Start)
    F{Does files and 
    folders exist?}
    style F fill:blue
    LG(Log to the error file)
    style LG fill:gray
    E(Raise an error)
    style E fill:red
    D(Partitioninng files)
    style D fill:orange
    CR{Are original and
    partition files
     consistent?}
    style CR fill:blue
    AN5(Find top 10 most 
    common names)
    style AN5 fill:green
    AN6(Find top 5 most 
    active users)
    style AN6 fill:green
    END(End)
    S ----> F
    F -->|yes| D
    F ---->|no| LG
    D -->CR
    CR ----> |yes| AN5
    CR ----> |no| LG
    LG ----> E
    E ----> END
    AN5 ----> AN6
    AN6 ----> END