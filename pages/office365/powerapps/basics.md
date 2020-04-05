---
title: Basics
layout: page
summary:
---

## Screen Navigation

> Navigate(DetailScreen,ScreenTransition.Fade)

## Combining Values

> ThisItem.Employee & " - " &ThisItem.Department

## Edit Screen

Add screen
Add Edit Form
Add data (table)
Edit fields

Add selected data from gallery:
> EmployeeGallery.Selected

## Dropdown Menu

Add screen, add "Input" "dropdown", Connect items to table (data), select column field.
Make values unique, use distict function:
> Distinct(empltbl,Office)

Sort alphabetically with the sort function
> Sort(Distinct(empltbl,Office),Result)

Display in a Text Field the dropdown selection
> DropdownOffice.Selected.Result

### Second Dropdown Menu with hierachy

> Distinct(Filter(empltbl,DropdownOffice.Selected.Result=Office),Employee)
(Enter formula with Alt+Enter to refresh)

## Variables

Screen Variable
> UpdateContext({Dep:"SHIIIIIIIT"})

Global Variable
> Set(GDep,"YEAH")

Set Global Variable to Dropdown Result
> Set(GDep,DropdownEmployee.SelectedText.Result)

Button sets a variable (result from calculation) and then navigates to other screen and sets new variable
> Set(Res,Result.Text);Navigate(DetailScreen,ScreenTransition.Fade,{Res2:Res})

