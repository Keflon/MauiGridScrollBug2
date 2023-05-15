# WinUI bug

## Auto-sized Grid row containing ScrollView containing a Rectangle ignores explicit HeightRequest on the Rectangle.

Given the following xaml:
```xaml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="MauiGridScrollBug2.MainPage">
    
    <Grid RowDefinitions="*,*">
        <ScrollView Grid.Row="0">
            <Rectangle HeightRequest="600" BackgroundColor="Blue"/>
        </ScrollView>
        <ScrollView Grid.Row="1">
            <Rectangle HeightRequest="600" BackgroundColor="Yellow"/>
        </ScrollView>
    </Grid>

</ContentPage>
```
### Expected result is 2 grid rows each with a Rectangle that can be scrolled up and down. 
![image](https://github.com/dotnet/maui/assets/16598898/276cc083-fe6b-46cd-8541-781d36f16fe3)


### Actual result for WinUI - the Rectangle instances are minimal height.
![image](https://github.com/dotnet/maui/assets/16598898/84da2f27-3260-4734-ad75-9c94dda9c647)

