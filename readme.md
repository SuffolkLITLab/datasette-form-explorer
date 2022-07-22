# Form explorer [Datasette](https://datasette.io/)

[Datasette](https://datasette.io/) is a data journalism tool that allows people
to quickly and easily share databases on the Internet.

## Dashboards

Currently we're using the [datasette-dashboards
plugin](https://datasette.io/plugins/datasette-dashboards)
for some simple visualizations. Charts, etc. use [Vega](https://vega.github.io/).
Vega has an interactive playground editor. You can experiment with queries from the
live datasette with something like the example here: [Open the Chart in the Vega Editor](https://vega.github.io/editor/#/url/vega-lite/N4IgJAzgxgFgpgWwIYgFwhgF0wBwqgegIDc4BzJAOjIEtMYBXAI0poHsDp5kTykBaADZ04JAKyUAVhDYA7EABoQAEzjQATjRyZ289AEEABBBoIcguIaZJ1h2DcyGA7nRiHETOMtXLDypJhUiioBKKigDOqCaBjYeIScDABmSWyCANb8qeoI-HAAHuZs6nDqlPDqbOkMSDg4lFBsCATZCAD6BUUlZVAQxAD8EACOggC8AMoAogAykwDCACoApABMAAySkTQQyjRQOnKrc6trjQyymAAUAFQAlCdIECdnFycAYgBKAPIAsidLYgAQq08oVBMVSgCACInADi3wAqgAFE6AgCaJ02mh2ewOshOXw+UMmH1RGPWL0wJ2J4zmADJgq0AmhQJgAJ44OAxXrEEAAXz5SmQ6nSMWs6mCcFkjV2sjILJA+QVSRocEEyhiWO2u32umC7M5MVkTRosiQ0SUSHy2wVgiQnkE+jlFjQawFSjZytV6u5bHOmH1HK56CGNQudACNFI-IFQA).

The linked example is just a barchart that shows the number of forms in each jurisdiction. You can
customize the SQL query and the kind of chart by playing with some of the examples.


## Prerequisites to running Datasette

Install the prerequisites for Datasette:

```bash
pip install datasette datasette-dashboards
```

Datasette is a self-contained Python app. To run, you just type
`datasette form_explorer.db`.

It will run on port 8001 by default; a link will be displayed on the command
prompt.

## Deploying to Heroku

In the directory where you clone this repository:

```bash
datasette publish heroku -n suffolk-form-explorer --install datasette-dashboards --metadata metadata.yml --template-dir templates form_explorer.db
```

This builds the app and deploys it Heroku.