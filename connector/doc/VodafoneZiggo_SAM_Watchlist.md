---
uid: Connector_help_VodafoneZiggo_SAM_Watchlist
---

# VodafoneZiggo SAM Watchlist

## About

The **VodafoneZiggo SAM Watchlist** connector is a virtual connector that acts as the central data store for the SAM Watchlist application. It holds the VTP nodes that operations are following up on, the nodes that are excluded from SAM handling, and the lookup data (issue types, triggers, process flows and team assignments) used to create consistent MICA/ICA tickets.

The connector does not poll any device. All data is created, edited and imported from the SAM Watchlist application, and the connector keeps it persistent and available to other DataMiner components.

## Key Features

- **Watchlist management**: Keeps track of VTP nodes under follow-up, including summary, trigger, incident, severity, region, impacted customers, issue type, frequency, size, process flow and the operator who created the entry.

- **Blacklist**: Excludes VTP nodes from SAM handling, for example holiday parks or care homes, with the group and reason for each node.

- **Configurable lookup tables**: Issue types, triggers and process flows are maintained centrally on the **Configuration** page, so operators always pick from the same list of values.

- **Consistent ticket summaries**: Each process flow defines a summary structure with placeholders (e.g. {vtp}, {issueType}, {severity}), so tickets created for MICA/ICA always follow the same format.

- **Team and contractor assignment**: The **Teams** table, imported from Excel, maps postcode areas to network areas, contractors, on-call experts and network operators.

## Use Cases

### Following Up on Problem Nodes

**Challenge**: Operators need a shared, persistent overview of VTP nodes that require attention, instead of tracking them in separate spreadsheets.

**Solution**: Watchlist entries are created from the SAM Watchlist application and stored in the connector, together with their severity, region, trigger and last modification time.

**Benefit**: All operators work from the same up-to-date list, and every change is traceable.

### Avoiding Unnecessary Tickets

**Challenge**: Some nodes, such as holiday parks or locations without service, regularly raise issues that should not be handled by SAM.

**Solution**: These nodes are added to the **Blacklist** table with their group and reason.

**Benefit**: Less noise for operators and fewer unnecessary tickets.

### Routing Issues to the Right Team

**Challenge**: Finding the right contractor or on-call expert for an affected area takes time.

**Solution**: The **Teams** table links each postcode area to its network area, damage contractors, FttH contractor, on-call experts and network operator.

**Benefit**: Faster and more accurate dispatching of issues.

## Technical Reference

### Prerequisites

- **DataMiner 10.4.0.0 (build 14003)** or higher is required.

- The **SAM Watchlist application** is needed to create, edit and import the data stored in this connector.

- No connection settings are required: the connector uses a **virtual** connection, so an element can be created without an IP address or port.
