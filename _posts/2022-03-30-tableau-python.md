---
layout: post
title: "Manipulating metadata in Tableau workbooks"
date: 2022-03-30
categories:
---

Say you work in an enterprise with a large number of Tableau workbooks and you need to identify all connections to a particular data source so you can migrate them over to a newer data source and retire the old one. While you're at it, you'd like to make some standard changes across these legacy workbooks so they adhere to an organzational standard theme. *What do you do?*

Your options are limited to the following:
* Pay for the [Data Management Add-On](https://www.tableau.com/products/data-management) and work with the [Metadata API](https://help.tableau.com/current/api/metadata_api/en-us/index.html). This is expensive and is limited to read-only capabilities, meaning you can extract your metadata but you can't make changes to it.
* Manually comb through every workbook and make the changes yourself. This could take several weeks if you have hundreds of workbooks, and human error could lead to reporting outages for dashboard users.
* **Modify the .twb files programatically**

## .twbs

What even is a Tableau Workbook (.twb) file? While seemingly a proprietary file type meant to obfuscate metadata and make vendor migration difficult (see, for instance, .pdf), a .twb is nothing more than a .xml file in disguise. Indeed, opening up a Tableau Workbook in a text editor confirms this structure. Moreover, a .twbx is simple a *zipped* .twb, along with saved files of any data sources the workbook connects to.

This structure makes it surprisingly easy to comb through Tableau Workbooks for metadata, make changes, and republish. One can imagine a world where companies that use Tableau manage the dashboard creation process fully programatically, à la Looker vis-à-vis LookML.

## Outline

The general structure of how the code interacts with a workbook is as follows:

1. Define a *Workbook* object to be a .twb file (and its contents).
2. Parse the Workbook as you would any other .xml file, by scanning the tags and extracting elements.
3. Identify patterns in the .xml for important elements, such as Custom SQL queries, fonts, and field references.
4. Save these attributes in a tabular format for easy querying.
5. Override attributes as desired.

## Limitations

The main limitation of this approach is that, for mass metadata manipulation, all of your Tableau Server Workbooks need to be saved in some central repository. If workbooks are saved on various machines and never organized before being published to the server, then you would need to first download all workbook files before continuing with this process.

## Potential

As mentioned previously, it would be cool to see if any organizations that use Tableau manage some aspects of the publishing process programatically. It wouldn't be hard to modify this code to be used in a CI/CD process that looks something like this:

1. Create a new Tableau Workbook with all the bells and whistles you want.
2. Commit the new workbook file to a version-controlled branch.
3. Submit a pull request to the main branch of your repo, triggering a CI job (Jenkins, GitHub Actions, etc.).
4. This CI job then checks to ensure your workbook follows some pre-defined standards: fonts must match, no custom SQL, no Excel connections, no pie charts, etc.
5. For any simple fixes, a Tableau "linter" modifies your file to conform to the standards and repackages/republishes it to the server.
6. For more involved fixes, the pull request is rejected with comments requiring changes.

## Code

Get the code below. Full disclaimer: this is old and hasn't been tested recently; some users have their own forks of the repo and may have resolved any outstanding bugs.

[TableauDesktopPy](https://github.com/bpewyllie/TableauDesktopPy)

***