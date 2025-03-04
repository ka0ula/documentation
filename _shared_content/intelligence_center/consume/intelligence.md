# Intelligence

## Introduction

Looking for a Threat actor? A specific Malware? A report on a topic of interest? Or a URL that looks suspicious? The Intelligence page possesses a search engine with complex filtering capabilities to navigate through millions of data. This threat knowledge base is updated on a daily basis by SEKOIA.IO analysts to make sure all kinds of threats are covered. 

The two ways to find what you need in the knowledge base is to: 

1. Use the search bar embedded in the header. It’s accessible from any page of the Intelligence Center and enables a quick search in the database. 
2. Click `Intelligence` from the Intelligence Center menu and use the main search bar to browse the knowledge you need.

![Intelligence-search](/assets/intelligence_center/intelligence%20search.png){: style="max-width:100%"}

## How to search

You can either search in all the database or only in the objects or the observables database. To do so, use the select on the left of the search bar to select the needed scope. 

### Tabs

After you’ve typed your search and clicked on `enter`, two tabs appear under the search bar: one for objects and one for observables. 

Each tab has a counter that informs users about the number of items in the database for each category. 

For instance, if you search for `Google`, you will find numerous objects (reports, Intrusion sets, Indicators…) but only two observables. 

!!! tip
    Always check both tabs to be sure to get all information needed on a topic. Observables may not be harmful but they can be helpful in an investigation.

## Search for objects

### How the search engine works

When searching for a term, SEKOIA.IO will list objects with fields that match the term. 

The following fields are taken into consideration by the search engine: 

- Name
- Description
- Aliases
- Content of a report
- External references
- The location’s country code (if the search term contains 2 characters)

By default, search results are sorted by **relevance**, but you can choose to display them by the last edition date.

!!! Tip
    When the search contains multiple words, it can be useful to see the results matching exactly what has been entered. Putting the search between quotes (`" "`) will search for objects containing the exact term in one of their fields.

### Table Columns

Search results are listed in a table with multiple columns. These columns can be shown or hidden in the filters panel, and users can change their order by dragging them using the `:` icon. 

By default, these columns are: 

| Column | Description |
| --- | --- |
| TLP | How sensitive is the information. Types of TLP in SEKOIA.IO: White, green, amber, red |
| Type | Type of object. Hover on the object icon to see the type of object |
| Name | Name of object. Hover on the name to read the full name |
| Sub-types | Some objects have sub-types like indicators, malware, reports, tool   |
| Confidence | How confident SEKOIA.IO is about this object |
| Sources | Where this object came from |
| Last edited | Date of last edition |
| Created | Date of creation |

To show or hide these columns, click on `Filters`, then `Select columns to show` and choose the ones needed.

### Pagination

Depending on your screen size, you can change the pagination of this data table. It is set to 10 results per page by default, but you can increase this number to 15, 25, 50 or 100. 

### Revoked objects

When a name is red in the table, it means that the object has been revoked.

### Filters for objects

To filter results in the Intelligence table, multiple filters are available to users. When a filter is selected, a tag is added on top of the table. 

This table lists all filters for objects in the Intelligence page. 

| Filter | Description |
| --- | --- |
| Type | Multiselect to choose types of object to show |
| Source | Search in more than 200 sources available. This field has autocomplete to help you select sources.  |
| Feed | Show only objects matching a feed that was created in the Feeds page |
| Confidence level | Show only objects equal to, higher than, below than, higher than or equal to, below or equal to a certain level of confidence |
| Observable type | Restrict indicators to only the ones with a pattern containing the selected observable types |
| Is a source | Display only identities that are sources of other objects |
| Last update | Filter objects updated in the last hour, last 24h, last 7 days, last 30 days, this year, all time |
| Creation date | Filter objects created in the last hour, last 24h, last 7 days, last 30 days, this year, all time.  |
| TLP | Show only object with a certain TLP |

To remove a filter, just click on the `cross` inside the tag. To remove all filters, click on `Clear filters` next to the tags’ list or in the bottom of the filters’ panel.

## Search for observables

When searching for observables, SEKOIA.IO will investigate the field `x_inthreat_short_display`, a custom attribute that is equal to the main value of the observable (`value` for IP, `name` for organizations, ...).

If the search is a hash, the search engine will consider the number of characters and look for the right hashes. 

| Type of Hash | Characters |
| --- | --- |
| MD5 | 32 |
| SHA-1 | 40 |
| SHA-256 | 64 |
| SHA-512 | 128 |

If the search is an IP CIDR, the search engine will look for the IPs contained in it: `185.213.83.0/24` will return `185.213.83.102`, `185.213.83.106`, ...

### Search for multiple observables

To search for a list of observables, you can paste a list of values and search for them in bulk (multiple lines). To skip a line and paste multiple observables, press `Shift-Enter` and paste your content. 

### Known and unknown observables

If you paste a list of observables in the search bar, chances are SEKOIA.IO will recognize some of them, but some may be unknown. 

To differentiate between the two, a tab with `Known` and `Unknown` helps understand which observables are in the database and which ones are not. 

### Filters

| Filter | Description |
| --- | --- |
| By type | A multiselect to choose types of observables to show in the listing |
| By tags | An autocomplete to filter observables list by tags |
| By sources | Search in more than 200 sources available. This field has autocomplete to help you select sources.  |

### Bulk actions

When you have a list of observables in your search results, you can select two or more of them by ticking the checkbox on the left of the value. Once selected, you can copy their values using the `copy` button that appears next to the filters. 


