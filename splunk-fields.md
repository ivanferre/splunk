## Splunk Fields

The Fields Sidebar shows all the fields extracted at search time. It differentiates between **Selected Fields** and **Interesting Fields**.

Default fields `host`, `source`, and `sourcetype` are selected by default.

At the left of the name of the Field, the letter `a` denotes a string value, and the number sign `#`, a numeral.

When selecting a field, it will be included in the current search, and it will persist in subsequent queries.

Field names are case-sensitive, but values are not.

The `| fields` command can be used to include or exclude fields in the search.

	index=web status IN ("500", "503", "505")
	| fields status
	| stats count by status

The `fields` command filters in the records that include a `status` field. We place this command before the `stats` command, so it will manage few records and be more efficient. Filtering as soon as possible in a search is a best practice.

The `fields` command may be used to indicate if the field must be included (as in `+status`) or excluded (`-status`). By default is `+fieldname`.

We may rename fields in the display results to make the output more meaningful to the users.

	index=web status IN ("500", "503, "505")
	| fields status
	| stats count by status
	| rename status as "HTTP Status", count as "Number of Events"

Some fields are extracted at index time, while others are extracted at search time.

When Splunk ingest data into the index, some fields are extracted. This includes metadata, such as `host`, `sourcetype`, and `source`, and internal fields as `_time` and `_raw` which contain the original timestamp and raw data of the event.

At search time, Field Discovery extracts additional fields from raw event data based on the assigned `sourcetype`, as well as `key=value` pairs found in the data. These fields are persisting, and will be extracted every time we query with the same search terms.

**Temporary fields** can be created using comands such as `eval`. `| eval` is used to create an manipulate field values.

	index=network sourcetype=cisco_wsa_squid
	| stats sum(sc_bytes) s Bytes by usage
	| eval bandwith = Bytes/1024/1024

The **Field Extractor** utility can be used to extracts from the data, that were not automatically extracted. By using the commands `rex` and `erex`, regular expressions may be used to access the data in a more flexible way.

To use `rex`, we need to know how to write down regular expressions (regex). To use `erex`, we need to supply examples of the matching items.

	index=games sourcetype=SimCubeBeta
	| erex Character fromfield=_raw examples="pixie, Kooby"

`erex` has the same limitation as automatic extraction: it only _knows_ what to do based on the sample examples it has been given.

By clicking on the `Job` menu, we may see the regex it has used, and we may use it as starting point to write one on our own, to use it with `rex`.

The `rex` command allows to use regex including capture groups to match field values or raw data at search time. It allows to match multiple groups resulting in multiple fields.

Using the `_raw` field has a large impact on performance. Always use an available field to extract data, if possible.

	index=games sourcetype=SimCubeBeta
	| rex field=_raw "^[^'\n]*(?P<User>[a-zA-Z0-9_.-]+\.[a-zA-Z0-9.]+)'\s[a-zA-Z:]+'(?<Character>[a-zA-Z0-9.-]+)"

regex is surrounded by double quotes. This regex creates a field called `User` that includes the email addresses, and a `Character` field to get the names.

`erex` is easier to use, does not require RegEx knowledge, but requires sample data to generate RegEx, and the user can take this RegEx as a starting point to use `rex`. When possible, it's better to use `rex`.

Temporary fields, which are not persisting, must be defined and typed for every search we want to perform. But storing this in **calculated fields**, we may overcome this.

Calculated fields can only use fields that have been returned by the search.

**Field aliases** allow to define another names for fields in your data. We may assign the same `alias` to different field names. This allows to make searches in _both_ fields. Aliases don't replace the original fields, so you can still use them to search.

**Lookouts** allow to add values and fields to the data. For instance, the description of the HTML requests codes.

The resolution order is:
1. Field Extractions
2. Field Aliases
3. Calculated Fields
4. Lookups
5. Event Types
6. Tags

References must always go upwards, from higher to lower-numbered levels.

LOOK FOR: Splunk RegEx, Knowledge Objects.


