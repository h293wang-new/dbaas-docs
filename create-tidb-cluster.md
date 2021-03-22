---
title: Create a TiDB Cloud cluster
summary: Learn how to create your TiDB Cloud cluster.
---

# Create a TiDB Cloud Cluster

This document describes how to create a TiDB Cloud cluster.

<EmbedYouTube videoTitle="TiDB Cloud - Create a Cluster" videoSrcURL="https://www.youtube.com/embed/uGRoKiETSUU?rel=0" />

1. Log in to TiDB Cloud.

    Open <https://tidbcloud.com> in a browser and sign in with your user name and password.

2. Select Cloud Provider.

    Click the cloud service provider icon on the left of the top navigation bar, and select the cloud provider. The existing options are Amazon Web Services and Google Cloud.

3. Access the **Create a Cluster** page.

    On the TiDB Cloud console's homepage, click **Create a Cluster**. The Create a Cluster page is displayed.

4. Set the cluster name and the root password.

    1. In the **Cluster Name** field, enter a name for your TiDB Cloud cluster.
    2. In the **Root Password** field, enter a root password.

5. Select **Region**.

    Click to select the region where your TiDB cluster is deployed. Future scaling will all be under the chosen region. You cannot change it after the cluster is created.

6. Select **Tier**.

    Click to select your cluster tier, which determines the throughput and performance of your cluster. You cannot change it after the cluster is created. See [Select Your Cluster Tier](select-cluster-tier.md) for details.

    > **Note:**
    >
    > TiDB Cloud Public Preview Free Trial users have access only to the t1.standard cluster tier.

7. Select the number of nodes.

    Set the number of your TiDB nodes and TiKV nodes respectively by clicking the plus or the minus sign. See [Size Your Cluster](size-your-cluster.md) for details.

    > **Note:**
    >
    > TiDB Cloud Public Preview Free Trial users cannot change the number of TiDB and TiKV nodes.

8. Click **Submit**.

    Your TiDB Cloud cluster will be successfully created in approximately 5-10 minutes.
