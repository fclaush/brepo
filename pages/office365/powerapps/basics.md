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

## Data Collections

Two Text Input fields and one button to collect data into "RatingCollection"
> Collect(RatingCollection,{ColTitle:TitleInput.Text,ColRating:RatingInput.Text})

Remove Item Trash Can
> Remove(RatingCollection,ThisItem)

Clear complete Data Collection
> Clear(RatingCollection)

Patch / edit data Collection
> Patch(RatingCollection,CollectionGallery.Selected,{ColRating:RatingInput.Text})

## Password Screen

Button Function, to check password, set variable, reset the password text field, check if password variable is true, then navigate
> If(pwinput.Text="password",UpdateContext({pvar:true}),UpdateContext({pvar:false}));Reset(pwinput);If(pvar,Navigate(Collections,ScreenTransition.Fade))

## Launch URLs Function

Column "Link" with URL, add function to icon.
> Launch(Link)