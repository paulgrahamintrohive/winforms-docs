---
title: Groups Collection
page_title: Groups Collection | UI for WinForms Documentation
description: Groups Collection
slug: winforms/gridview/grouping/groups-collection
tags: groups,collection
published: True
position: 3
---

# Groups Collection



When a group is created it is added to the *Groups* collection of the corresponding template. You can access the groups collection in the following way:#_[C#] Accessing groups_

	



{{source=..\SamplesCS\GridView\Grouping\Grouping.cs region=accessGroups}} 
{{source=..\SamplesVB\GridView\Grouping\Grouping.vb region=accessGroups}} 

````C#
            DataGroupCollection templateGroupCollection = this.radGridView1.MasterTemplate.Groups;
````
````VB.NET
        Dim templateGroupCollection = Me.RadGridView1.MasterTemplate.Groups
        '
````

{{endregion}} 




You can expand and collapse groups programmatically. The code blocks below demonstrate how you can expand and collapse the first group in the *Groups* collection.#_[C#] Expanding groups_

	



{{source=..\SamplesCS\GridView\Grouping\Grouping.cs region=expandGroups}} 
{{source=..\SamplesVB\GridView\Grouping\Grouping.vb region=expandGroups}} 

````C#
            this.radGridView1.Groups[0].Expand();
````
````VB.NET
        Me.RadGridView1.Groups(0).Expand()
        '
````

{{endregion}} 


#_[C#] Collapse groups_

	



{{source=..\SamplesCS\GridView\Grouping\Grouping.cs region=collapseGroups}} 
{{source=..\SamplesVB\GridView\Grouping\Grouping.vb region=collapseGroups}} 

````C#
            this.radGridView1.Groups[0].Collapse();
````
````VB.NET
        Me.RadGridView1.Groups(0).Collapse()
        '
````

{{endregion}} 




You can use __AllowGroup__ property of each column to indicate whether the user will be able to group by this column or not. The default value is *true*.#_[C#] Allow groups_

	



{{source=..\SamplesCS\GridView\Grouping\Grouping.cs region=allowGroup}} 
{{source=..\SamplesVB\GridView\Grouping\Grouping.vb region=allowGroup}} 

````C#
            this.radGridView1.Columns["Country"].AllowGroup = false;
````
````VB.NET
        Me.RadGridView1.Columns("Country").AllowGroup = False
        '
````

{{endregion}} 




## DataGroup class

DataGroup collections have hierarchical structure. One or more group levels could be created. Properties of the DataGroup give access to its *Level*, *Parent* and *Child* groups:#_[C#] Accessing parent/child groups_

	



{{source=..\SamplesCS\GridView\Grouping\Grouping.cs region=accessingParentChildGroups}} 
{{source=..\SamplesVB\GridView\Grouping\Grouping.vb region=accessingParentChildGroups}} 

````C#
            int groupLevel= this.radGridView1.Groups[0].Level;
            Group<GridViewRowInfo> parentGroup = this.radGridView1.Groups[0].Parent;
            DataGroupCollection groups = this.radGridView1.Groups[0].Groups;
````
````VB.NET
        Dim groupLevel As Integer = Me.RadGridView1.Groups(0).Level
        Dim parentGroup As Group(Of GridViewRowInfo) = Me.RadGridView1.Groups(0).Parent
        Dim groups As DataGroupCollection = Me.RadGridView1.Groups(0).Groups
        '
````

{{endregion}} 




The header row of a group (*GridViewGroupRowInfo*) can be accessed using the __GroupRow__ property
      	for a particular data group, for example:#_[C#] Accessing group header row_

	



{{source=..\SamplesCS\GridView\Grouping\Grouping.cs region=groupHeaderRow}} 
{{source=..\SamplesVB\GridView\Grouping\Grouping.vb region=groupHeaderRow}} 

````C#
            GridViewRowInfo groupHeaderRow = radGridView1.Groups[0].GroupRow;
````
````VB.NET
        Dim groupHeaderRow = Me.RadGridView1.Groups(0).GroupRow
        '
````

{{endregion}} 


