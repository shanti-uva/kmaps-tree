# Kmaps Tree

This project contains a small jQuery plugin using [fancytree](https://github.com/mar10/fancytree) to display the hierarchical tree for the SHANTI Knowledge Maps applications, you can read more [here](https://shanti.virginia.edu/wordpress/?page_id=4023) and visit the [Mandala tools here](https://mandala.shanti.virginia.edu/), the hierarchy tree you see on the site fly-out is what this plug-in is in charge of.

## Getting Started

To add this plug-in to your Kmaps application you can download the code from the git repository:
* [https://github.com/shanti-uva/kmaps-tree](https://github.com/shanti-uva/kmaps-tree)

You can clone it or just download the jQuery plug-in.

### Prerequisites

The plug-in requires:

* Kmaps app (this plug-in was designed for the KMAPS apps so you need an instance for it to run)
* Solr index where the tree data is stored (and consulted)
* [fancytree](https://github.com/mar10/fancytree)

You'll notice that there is now CSS provided, it should be part of your KMAPS app.

### How to use it:

```
$(document).ready(function(){
        $("#tree").kmapsTree({
          termindex_root: "HTTPS://SERVER/PATH/TO/TERM_INDEX",
          kmindex_root: "HTTPS://SERVER/PATH/TO/ASSETS_INDEX",
          type: "YOUR_APP_TYPE", //[subjects,places,sources, etc.]
          root_kmap_path: '/', //the path to the root node (leave blank if not needed)
          baseUrl: "HTTPS://PATH/TO/NODE/%%ID%%", //This base URL is a pattern with the %%ID%% to be replaced with each node's ID
          expand_path: "", //if we want the tree to be expanded to a specific path from the start
          perspective: "", // the perspective code to use  [pol.admin.hier, cult.reg, elect.rel, etc.]
          activeNodeId: "" // If we want a specific node to be active from the start
        });
});
```

The baseURL option requires you to define the URL and use the pattern %%ID%% that will be replaced by the id of each node respectively. It was designed this way so it would work for Rails applications that have the format:

`HTTPS://SERVER/features/ID`

And for the Drupal applications that have the following format:

`HTTPS://SERVER/APP/%%ID%%/OVERVIEW/NOJS`

Just make sure you have the %%ID%% pattern in your baseUrl option.

## Authors

* *Initial work* - [Yuji](https://github.com/ys2n)
* *Initial work* - [Ed](https://github.com/torma)
* Modifications - [Derik](https://github.com/rderik)


## Acknowledgements

* To everyone at [SHANTI](https://github.com/orgs/shanti-uva/people)
