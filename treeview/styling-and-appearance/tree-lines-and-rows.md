---
title: Tree Lines and Rows
page_title: Tree Lines and Rows | UI for WinForms Documentation
description: Tree Lines and Rows
slug: winforms/treeview/styling-and-appearance/tree-lines-and-rows
tags: tree,lines,and,rows
published: True
position: 1
---

# Tree Lines and Rows



## 

To display lines connecting nodes in RadTreeView set the __ShowLines__property to true. Control the appearance of the lines
          using the __LineStyle__ and __LineColor__ properties. __LineStyle__is
          of type __TreeLineStyle__ and includes the following members __Solid__, __Dash__,
          __Dot__, __DashDot__, __DashDotDot__.
        #_[C#] _

	



{{source=..\SamplesCS\TreeView\GettingStarted.cs region=lines}} 
{{source=..\SamplesVB\TreeView\TreeViewGettingStarted.vb region=lines}} 

````C#
            
            radTreeView1.ShowLines = true;
            radTreeView1.LineStyle = TreeLineStyle.DashDot;
````
````VB.NET
        RadTreeView1.ShowLines = True
        RadTreeView1.LineStyle = TreeLineStyle.DashDot
        '
````

{{endregion}} 


![treeview-styling-and-appearance-tree-lines-and-rows 001](images/treeview-styling-and-appearance-tree-lines-and-rows001.png)

To select rows spanning the entire width of RadTreeView (rather than just the node label), set the __FullRowSelect__property
          to true and __ShowLines__ to false. In addition you can set the alternating row color by setting the
          __AllowAlternatingRowColor__ and __AlternatingRowColor__ properties.
        #_[C#] _

	



{{source=..\SamplesCS\TreeView\GettingStarted.cs region=AlternatingRowColor}} 
{{source=..\SamplesVB\TreeView\TreeViewGettingStarted.vb region=AlternatingRowColor}} 

````C#
        
            radTreeView1.TreeViewElement.AllowAlternatingRowColor = true;
            radTreeView1.TreeViewElement.AlternatingRowColor = Color.LightBlue;
````
````VB.NET
        RadTreeView1.TreeViewElement.AllowAlternatingRowColor = True
        RadTreeView1.TreeViewElement.AlternatingRowColor = Color.LightBlue
        '
````

{{endregion}} 


![treeview-styling-and-appearance-tree-lines-and-rows 002](images/treeview-styling-and-appearance-tree-lines-and-rows002.png)