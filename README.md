# Bountyworkflow
Streamline bounty methodology here

## <br> pull latest data from CHAOS - PD
wget "https://chaos-data.projectdiscovery.io/index.json" && cat index.json | grep "URL" | sed 's/"URL": "//;s/",//' | while read host do;do wget "$host";done && for i in `ls -1 | grep .zip$`; do unzip $i; done && rm *.zip && cat *.txt >> alltargets.txt
