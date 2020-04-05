---
title: Basics
layout: page
summary:
---

## Screen Navigation

> Navigate(DetailScreen,ScreenTransition.Fade)

## Combining Values

> ThisItem.Employee & " - " &ThisItem.Department
> ThisItem.FirstName & " " & LastName

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

## Radio Button Selection
> ["Fun","Hate","Chill"]

> RadioState.Selected.Value

## Edit vs New Form
[Edit vs New Form](images\edit_new_if_text.png)
Intro to Canvas Apps > Create an App from a Template > Quick Changes to a Form
> If(EditForm1.Mode = FormMode.New, "Create a record", "Edit " & BrowseGallery1.Selected.FirstName)

## Currecy & Number Format
> Text(Value(ThisItem.Amount),"[$-en-GB]$#,###.00")

## Sort a Gallery
Replace value "amount" by value "FirstName" to sort by first name.
[Sort Gallery By](images\sort_gallery_by.png)

Sort by First Name first and Last Name second.
> SortByColumns(Search([@Purchases], TextSearchBox1.Text, "Amount","FirstName","LastName"), "FirstName", If(SortDescending1, Descending, Ascending),"LastName",Ascending)

## SharePoint Forms

Show on View DropdownEmployee
> If(SharePointForm1.Mode = FormMode.View,true,false)

[Make other cards visibility dependend on first one](images\pa_card_visible.png)

