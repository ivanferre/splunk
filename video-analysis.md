# Splunk BOTS - Boss Of The SOC (v3) Walkthrough & Analysis

Source: <https://www.youtube.com/watch?v=RXDbir6B5mE>

    | metadata type=sourcetypes index=botsv3 
    | stats values(sourcetype)

Lists all available sourcetypes.

    | metasearch index=botsv3 sourcetype=aws:* login

    index=botsv3 sourcetype=aws:cloudtrail
    | head 10000

    index=botsv3 sourcetype=aws:cloudtrail user_type="IAMUser"
    | stats values(userName) as User

    index=botsv3 sourcetype=aws:cloudtrail user_type="IAMUser"
    | stats values(userName) as u
    | nomv u
    |   rex mode=sed field=u "s/\s/,/g"
