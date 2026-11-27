# Detection rules — validation required

`local_rules.xml` is an illustrative starting point, not a production-ready ruleset.

Before use:
1. Back up `/var/ossec/etc/rules/local_rules.xml`.
2. Inspect the actual alert JSON and decoded fields for your Wazuh version.
3. Confirm parent rule IDs in the installed ruleset.
4. Test representative raw events with `/var/ossec/bin/wazuh-logtest`.
5. Adjust rule conditions to reduce false positives.
6. Restart the manager only after configuration validation.
7. Confirm alerts appear as expected and document test evidence.

Do not claim a rule is implemented or validated until it has fired correctly against a controlled test event.
