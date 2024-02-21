# dmarc-visualizer

To run this code, navigate to the correct directory using cd
with Docker Desktop open, run docker-compose up

DMARC files are saved to the ./files folder via Apple Automator. The script to run the automation is located at /Users/bryanmoore/Library/LaunchAgents/com.bryanmoore.runmailscript.plist

The automation itself is an automator app, found at /Applications/dmarc-automator


Analyse and visualize DMARC results using open-source tools.

* [parsedmarc](https://github.com/domainaware/parsedmarc) for parsing DMARC reports,
* [Elasticsearch](https://www.elastic.co/) to store aggregated data.
* [Grafana](https://grafana.com/) to visualize the aggregated reports.

See the full blog post with instructions at https://debricked.com/blog/2020/05/14/analyse-and-visualize-dmarc-results-using-open-source-tools/.

## Screenshot

![Screenshot of Grafana dashboard](/big_screenshot.png?raw=true)
