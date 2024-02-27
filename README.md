# dmarc-visualizer

To run this code, navigate to the correct directory using cd
with Docker Desktop open, run docker-compose up

DMARC files are saved to the ./files folder via Apple Automator (Users/bryanmoore/Applications/dmarc-automator). The script to run the automation is located at /Users/bryanmoore/Library/LaunchAgents/com.bryanmoore.runmailscript.plist. The script is scheduled to run at 9 AM, 12 PM, and 3PM daily.

-- to load the script:                  launchctl load ~/Library/LaunchAgents/com.bryanmoore.runmailscript.plist
-- to offload/unpack the script:        launchctl unload ~/Library/LaunchAgents/com.bryanmoore.runmailscript.plist
-- to check the status of the script:   launchctl print gui/$(id -u)/com.bryanmoore.runmailscript

Logs of the Automator app are located at /GitHub/dmarc-visualizer/logs/script_log.txt


Analyse and visualize DMARC results using open-source tools.

* [parsedmarc](https://github.com/domainaware/parsedmarc) for parsing DMARC reports,
* [Elasticsearch](https://www.elastic.co/) to store aggregated data.
* [Grafana](https://grafana.com/) to visualize the aggregated reports.

See the full blog post with instructions at https://debricked.com/blog/2020/05/14/analyse-and-visualize-dmarc-results-using-open-source-tools/.

## Screenshot

![Screenshot of Grafana dashboard](/big_screenshot.png?raw=true)
