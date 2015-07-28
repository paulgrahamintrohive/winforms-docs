---
title: Events
page_title: Events | UI for WinForms Documentation
description: Events
slug: winforms/gridview/sorting/events
tags: events
published: True
position: 4
---

# Events



## 

There are two events that are raised when the data in the RadGridView is sorted. The first one is the __SortChanging__ event which
        	is raised before the data is sorted. The second one is the __SortChanged__ event and it is raised after the data is sorted
        #_[C#]_

	

#_[C#]_

	

#_[VB.NET]_

	



From the event arguments of both events you can access the following data:

* __Action__ – an enumeration with values: *Add*, *Remove*, *ItemChanged* 
		  		and *Reset*The __Action__ property notifies if a __SortDescriptor__ is added, removed, modified or 
		    	the __SortDescriptors__ collection is cleared.
		    

* __NewItems__ - is a List of added, edited or removed __SortDescriptors__. For each __SortDescriptor__ you can
		  	get its __PropertyName__ and __Direction__

You are also able to cancel the sorting operation by setting the __Cancel__ property to *True*

{{source=..\SamplesCS\GridView\Sorting\SortingEvents.cs region=SortingEvents}} 
{{source=..\SamplesCS\GridView\Sorting\SortingEvents.cs region=SortingEvents1}} 
{{source=..\SamplesVB\GridView\Sorting\SortingEvents.vb region=SortingEvents}} 

{{source=..\SamplesCS\GridView\Sorting\SortingEvents.cs region=CancelSorting}} 
````C#
        private void radGridView1_SortChanging1(object sender, GridViewCollectionChangingEventArgs e)
        {
            e.Cancel = true;
        }
````
````VB.NET
    Private Sub RadGridView1_SortChanging(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangingEventArgs) Handles RadGridView1.SortChanging

    End Sub

    Private Sub RadGridView1_SortChanged(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangedEventArgs) Handles RadGridView1.SortChanged

    End Sub
    '
````

{{endregion}} 


#_[VB.NET]_

	



Since the __SortDescriptors__ collection implements the __INotifyPropertyChanged__ interface, you can use its __CollectionChanged__ event:

{{source=..\SamplesVB\GridView\Sorting\SortingEvents.vb region=CancelSorting}} 

{{source=..\SamplesCS\GridView\Sorting\SortingEvents.cs region=CollectionChanged}} 
````C#
            this.radGridView1.SortDescriptors.CollectionChanged += new Telerik.WinControls.Data.NotifyCollectionChangedEventHandler(SortDescriptors_CollectionChanged);
````
````VB.NET
    Private Sub RadGridView1_SortChanging1(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangingEventArgs) Handles RadGridView1.SortChanging
        e.Cancel = True
    End Sub
    '
````

{{endregion}} 


#_[C#]_

	



{{source=..\SamplesCS\GridView\Sorting\SortingEvents.cs region=CollectionChanged1}} 
{{source=..\SamplesVB\GridView\Sorting\SortingEvents.vb region=CollectionChanged}} 

````C#
        void SortDescriptors_CollectionChanged(object sender, Telerik.WinControls.Data.NotifyCollectionChangedEventArgs e)
        {
            
        }
````
````VB.NET
        AddHandler Me.RadGridView1.SortDescriptors.CollectionChanged, AddressOf SortDescriptors_CollectionChanged
        '
````

{{endregion}} 


#_[VB.NET]_

	



The arguments of this event provide the same data as the __SortChanged__ event.