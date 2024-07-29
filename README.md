<!DOCTYPE html>
<html>
<head>
    <title>Harvest Work Hours Monitor</title>
</head>
<body>
    <h1>Harvest Work Hours Monitor</h1>
    <p>The Harvest Work Hours Monitor is an Azure DevOps dashboard widget that visualizes billable, internal (non-billable), and R&D hours logged through the Harvest app. This widget helps teams efficiently track and manage time spent on various project categories.</p>
    <img src="https://github.com/user-attachments/assets/6390ea03-1876-4c0c-9e11-74c17d834461" alt="Harvest Work Hours Monitor Image">

    <h2>Features</h2>
    <ul>
        <li><strong>Billable Hours</strong>: Displays hours that are chargeable to clients or projects, providing insight into revenue-generating activities.</li>
        <li><strong>Internal Hours</strong>: Tracks hours dedicated to internal tasks such as meetings, training, and administration, crucial for understanding resource allocation.</li>
        <li><strong>R&D Hours</strong>: Captures hours for research and development projects, identified by a project code containing "R&D", regardless of whether these hours are billable or internal.</li>
    </ul>

    <h2>Configuration</h2>
    <p>To configure the widget, click on the gear icon in the widget's header. You'll need to provide:</p>
    <ul>
        <li><strong>Harvest Account ID</strong>: This is your unique account identifier for the Harvest app, which is required to fetch time entries.</li>
        <li><strong>Authorization Token</strong>: A personal access token necessary for authenticating requests to the Harvest API.</li>
        <li><strong>Display Mode</strong>: Choose between displaying data as a percentage or in absolute hours.</li>
    </ul>
    <img src="https://github.com/user-attachments/assets/1a19f106-d676-4217-a155-301add23d780" alt="Configuration Screenshot">

    <h2>Installation and Setup</h2>
    <ol>
        <li><strong>Install the Widget</strong>: Download and install the Harvest Work Hours Monitor from the Azure DevOps Marketplace.</li>
        <li><strong>Add to Dashboard</strong>: Drag and drop the widget onto your desired dashboard.</li>
        <li><strong>Enter Configuration Details</strong>: Provide your Harvest Account ID and Authorization Token to enable data fetching.</li>
        <li><strong>Customize Display Options</strong>: Select your preferred display mode to visualize the data effectively.</li>
    </ol>

    <h2>Usage</h2>
    <p>After configuration, the widget provides a real-time breakdown of hours spent on different types of work. This allows teams and managers to monitor resource utilization and focus, ensuring that project hours are appropriately categorized and tracked.</p>

    <h2>Privacy and Access</h2>
    <p>This widget is a private tool intended for use only by organizations with which it has been explicitly shared. It is not available publicly and should not be redistributed without proper authorization. Ensure that your organization complies with any sharing restrictions associated with this widget.</p>

    <p>For further assistance or detailed documentation, please visit <a href="https://github.com/BogdanBrat/DevOpsWidgetHarvest/tree/main">GitHub Page</a>.</p>
</body>
</html>
