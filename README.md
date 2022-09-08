# Embedding API Hands-on

In this practical hands-on we are going to embed a dashboard or two using the Tableau Embedding API v3

## Prerequisites

To ensure the dashboards load properly when embedded set the size of your dashboard on Tableau Public to the Generic Desktop (1366 x 768) size

## Step 1: Fork the repository

Go to the [sample repository](https://bit.ly/embeddingHandsOn) and fork the repository. Forking will create your own copy of the code.

## Step 2: Add the Embedding API v3 script

In your newly created repository code, edit the index.html file. We will first add the Embedding API v3 script at line 15

```
<script
    type="module"
    src="https://public.tableau.com/javascripts/api/tableau.embedding.3.latest.js"
></script>
```

## Step 3: Add the URL for the Tableau view

In the index.html file, add the URL for the dashboard to the `tableau-viz` object. The `tableau-viz` object starts at line 75. The view URL should be obtained from the Share menu of the dashboard and it should be added in line 79 replacing `[VIEW_URL]`
The final `tableau-viz` object will look similar to the following, assuming the dashboard URL is https://public.tableau.com/views/Sample-Superstore/Superstore

```
<tableau-viz
    device="default"
    hide-tabs=""
    id="tableauViz"
    src="https://public.tableau.com/views/Sample-Superstore/Superstore"
    style="width: 100%; height: 100%"
    toolbar="bottom"
    >
</tableau-viz>
```

## Step 4: Add a button to export cross-tab

In the index.html file, let us add an action to the Export Data button. We will be adding an action to the `onclick` function as follows: `onclick="document.getElementById('tableauViz').displayDialogAsync('export-cross-tab')"` The code for the Export Data button starting at line 62 will look similar to the following:

```
<button
    onclick="document.getElementById('tableauViz').displayDialogAsync('export-cross-tab')"
    class="button-30"
    style="width: 20%"
    >
    Export Data
</button>
```

## Step 5: Add logic to two other buttons

Add logic to Export PDF and Get Image buttons based on the [Tableau Embedding API reference for Viz object] (https://help.tableau.com/current/api/embedding_api/en-us/reference/interfaces/viz.html)

## Step 6: Add a new dashboard to another slide at line 97

## Next Step: Go have fun embedding!!
