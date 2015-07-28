---
title: Events
page_title: Events | UI for WinForms Documentation
description: Events
slug: winforms/gridview/grouping/events
tags: events
published: True
position: 7
---

# Events



## 

There are two events that are raised, when the data in the RadGridView is grouped. The first one is the __GroupByChanging__ 
        	event which is raised before the data is grouped and he second one is the __GroupByChanged__ event raised after the data is grouped.
        #_[C#]_

	

#_[C#]_

	

#_[VB.NET]_

	



From the event arguments of both events you can access the following data:

* __Action__ - an enumeration with values: *Add*, *Remove*, 
		  		*ItemChanged* and *Reset*.The __Action__ property notifies if
		  		a __GroupDescriptor__ is added, removed, modified or the __GroupDescriptors__ collection is cleared.
		  

* __NewItems__ - a List of *added*, *edited* or 
		  	*removed*__GroupDescriptors__. For each __GroupDescriptor__ 
		  	you can get its __GroupNames__, __Format__, __Aggregates__ and __Expression__.
		 

You are also able to cancel the grouping operation by setting the __Cancel__ property to *True*

{{source=..\SamplesCS\GridView\Grouping\GroupingEvents.cs region=subscribeToEvents}} 
{{source=..\SamplesCS\GridView\Grouping\GroupingEvents.cs region=eventHandlers}} 
{{source=..\SamplesVB\GridView\Grouping\GroupingEvents.vb region=eventHandlers}} 

{{source=..\SamplesCS\GridView\Grouping\GroupingEvents.cs region=cancelGrouping}} 
````C#
        void radGridView1_GroupByChanging1(object sender, Telerik.WinControls.UI.GridViewCollectionChangingEventArgs e)
        {
            e.Cancel = true;
        }
````
````VB.NET
    Private Sub RadGridView1_GroupByChanged(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangedEventArgs) Handles RadGridView1.GroupByChanged

    End Sub

    Private Sub RadGridView1_GroupByChanging(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangingEventArgs) Handles RadGridView1.GroupByChanging

    End Sub
    '
````

{{endregion}} 


#_[VB.NET]_

	



Since the __GroupDescriptors__ collection implements the __INotifyPropertyChanged__ interface, 
			you can use its __CollectionChanged__ event:
		

{{source=..\SamplesVB\GridView\Grouping\GroupingEvents.vb region=cancelGrouping}} 

{{source=..\SamplesCS\GridView\Grouping\GroupingEvents.cs region=subscribeToCollectionChanged}} 
````C#
            radGridView1.GroupDescriptors.CollectionChanged += new Telerik.WinControls.Data.NotifyCollectionChangedEventHandler(GroupDescriptors_CollectionChanged);
````
````VB.NET
    Private Sub RadGridView1_GroupByChanging1(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangingEventArgs) Handles RadGridView1.GroupByChanging
        e.Cancel = True
    End Sub
    '
````

{{endregion}} 


#_[C#]_

	



{{source=..\SamplesCS\GridView\Grouping\GroupingEvents.cs region=CollectionChangedHandler}} 
{{source=..\SamplesVB\GridView\Grouping\GroupingEvents.vb region=subscribeToCollectionChanged}} 

````C#
        void GroupDescriptors_CollectionChanged(object sender, Telerik.WinControls.Data.NotifyCollectionChangedEventArgs e)
        {

        }
````
````VB.NET
        AddHandler Me.RadGridView1.GroupDescriptors.CollectionChanged, AddressOf GroupDescriptors_CollectionChanged
        '
````

{{endregion}} 


#_[VB.NET]_

	



The arguments of this event provide the same data as the __GroupByChanged__ event.