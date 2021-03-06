# spo contenttype add

Adds a new list or site content type

## Usage

```sh
spo contenttype add [options]
```

## Options

Option|Description
------|-----------
`--help`|output usage information
`-u, --webUrl <webUrl>`|Absolute URL of the site where the content type should be created
`-l, --listTitle [listTitle]`|Title of the list where the content type should be created (if it should be created as a list content type)
`-i, --id <id>`|The ID of the content type. Determines the parent content type
`-n, --name <name>`|The name of the content type
`-d, --description [description]`|The description of the content type
`-g, --group [group]`|The group with which the content type should be associated
`-o, --output [output]`|Output type. `json|text`. Default `text`
`--verbose`|Runs command with verbose logging
`--debug`|Runs command with debug logging

!!! important
    Before using this command, connect to a SharePoint Online tenant admin site, using the [spo connect](../connect.md) command.

## Remarks

To create a content type, you have to first connect to a SharePoint site using the [spo connect](../connect.md) command, eg. `spo connect https://contoso.sharepoint.com`.

If the specified content type already exists, you will get a _A duplicate content type "Your Content Type" was found._ error.

The ID of the content type specifies the parent content type from which this content type inherits.

## Examples

Create a site content type that inherits from the List item content type

```sh
spo contenttype add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --name 'PnP Alert' --id 0x01007926A45D687BA842B947286090B8F67D --group 'PnP Content Types'
```

Create a list content type that inherits from the List item content type

```sh
spo contenttype add --webUrl https://contoso.sharepoint.com/sites/contoso-sales --listTitle Alerts --name 'PnP Alert' --id 0x01007926A45D687BA842B947286090B8F67D
```

## More information

- Content Type IDs: [https://docs.microsoft.com/en-us/previous-versions/office/developer/sharepoint-2010/aa543822(v%3Doffice.14)](https://docs.microsoft.com/en-us/previous-versions/office/developer/sharepoint-2010/aa543822(v%3Doffice.14))