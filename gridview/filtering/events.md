---
title: Events
page_title: Events | UI for WinForms Documentation
description: Events
slug: winforms/gridview/filtering/events
tags: events
published: True
position: 7
---

# Events



## 

There are two events that are raised  when the data in the RadGridView is filtered. The first one is the __FilterChanging__ event
          and it is raised before the data is filtered. The second one is the __FilterChanged__ event which is raised after
          the data is filtered.
        #_[C#]_

	

#_[C#]_

	

#_[VB.NET]_

	



From the event arguments of both events you can access the following data:

* __Action__ – an enumeration with values: *Add*, *Remove*,
              *ItemChanged* and *Reset*. The __Action__ property notifies
              if a __FilterDescriptor__ is *added*, *removed*,
              *modified* or the __FilterDescriptors__ collection is *cleared*.
            

* __NewItems__ - List of added, edited or removed __FilterDescriptors__.
              For each __FilterDescriptor__ you can get its *PropertyName*, *Operator*,
              *Value* and *Expression*.
            

You are also able to cancel the filtering operation by setting the __Cancel__ property to *True*.
        

{{source=..\SamplesCS\GridView\Filtering\Filtering Events.cs region=events}} 
{{source=..\SamplesCS\GridView\Filtering\Filtering Events.cs region=events1}} 
{{source=..\SamplesVB\GridView\Filtering\Filtering Events.vb region=events}} 

{{source=..\SamplesCS\GridView\Filtering\Filtering Events.cs region=cancelFilteringEvent}} 
````C#
        void radGridView1_FilterChanging1(object sender, Telerik.WinControls.UI.GridViewCollectionChangingEventArgs e)
        {
            e.Cancel = true;
        }
````
````VB.NET
    Private Sub RadGridView1_FilterChanging(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangingEventArgs) Handles RadGridView1.FilterChanging

    End Sub

    Private Sub RadGridView1_FilterChanged(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangedEventArgs) Handles RadGridView1.FilterChanged

    End Sub
    '
````

{{endregion}} 


#_[VB.NET]_

	



Since the __FilterDescriptors__ collection implements the __INotifyCollectionChanged__ interface,
          you can use its __CollectionChanged__ event:
        

{{source=..\SamplesVB\GridView\Filtering\Filtering Events.vb region=cancelFilteringEvent}} 

{{source=..\SamplesCS\GridView\Filtering\Filtering Events.cs region=collectionChanged}} 
````C#
            this.radGridView1.FilterDescriptors.CollectionChanged += new Telerik.WinControls.Data.NotifyCollectionChangedEventHandler(FilterDescriptors_CollectionChanged);
````
````VB.NET
    Private Sub RadGridView1_FilterChanging1(ByVal sender As Object, ByVal e As Telerik.WinControls.UI.GridViewCollectionChangingEventArgs) Handles RadGridView1.FilterChanging
        e.Cancel = True
    End Sub
    '
````

{{endregion}} 


#_[C#]_

	



{{source=..\SamplesCS\GridView\Filtering\Filtering Events.cs region=collectionChanged1}} 
{{source=..\SamplesVB\GridView\Filtering\Filtering Events.vb region=collectionChanged}} 

````C#
        void FilterDescriptors_CollectionChanged(object sender, Telerik.WinControls.Data.NotifyCollectionChangedEventArgs e)
        {
            
        }
````
````VB.NET
        AddHandler Me.RadGridView1.FilterDescriptors.CollectionChanged, AddressOf FilterDescriptors_CollectionChanged
        '
````

{{endregion}} 


#_[VB.NET]_

	



The arguments of this event provide the same data as the __FilterChanged__ event.
        