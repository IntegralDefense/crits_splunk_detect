### Splunk Detect Scripts
Managing tens of saved searches is difficult within splunk, this framework allows you to understand what coverage you have (indicator to log matrix), easily add additional searches, and have any matches sent to ACE for alert triage. Simply update the lookuptables on a regular basis with new indicators and your atomic indicator detection is covered.

### Prerequisites
The following assumes the code is cloned to /opt/splunk_detect
- cd /opt/splunk_detect
- git clone https://github.com/IntegralDefense/splunklib.git splunklib
- git clone https://github.com/IntegralDefense/ACE_client_lib.git saq

### Setup Steps
- create a Master csv file (example: Splunk_Search_Master.csv)
- configure splunk_detect.cfg (add splunk server & creds, ACE server & creds)
- make sure lookup tables are available on the splunk system that are referenced in the csv
- test the csv file "python3 master_search_file.py -f Splunk_Search_Master.csv -p"
- you should be able to copy and paste the search into splunk to verify the search syntax
- setup the crontab, verify the detect_wrapper.sh is correct (in case you changed any file names)

