---
title: "Scanning the Code"
chapter: true
weight: 5
---
# Scanning the Code

Now that the **CAST Highlight Code Reader** is launched (if not you should find it in your Windows/EC2 *Start Menu*), you'll see how easy the scanning process actually is. All you need to do is select the location where you have unzipped the source code of the first application:
![Folder Selection](/images/Scan-1.png)

{{% notice info %}}
At this stage, we only want to scan one of the applications. We could scan both of them together, but then their results would be bundled up together as a single application. In fact, the notion of ***Application*** relates to a set of files for which you want to see results calculated and displayed, separate from other applications.
{{% /notice %}}

## The Execution

Click on ***Launch Scan*** and you'll see the Code Reader go through the ***Discovery*** phase where it identifies the types and number of files that are present in the repository. It will then proceed to analyze every file that is deemed relevant, after which it will let you know it's done and give you a recap:
![Scan Results](/images/Scan-3.png)
Since we're happy with the results, you can click on ***SAVE RESULTS***. You'll be prompted to choose a location to store the scan's results. The resulting .zip file will be located there.
![Result File](/images/Scan-6.png)

You can go back to the start and repeat the process with the second application, after which you should have two *scan_results_YYYY_MM_DD-HH_MI_SS.zip* files.

### Onto the upload
All we have left to do is send our results to the SaaS portal...