# How to bind and control the selected row index on SfDataGrid using the MVVM pattern.

This article demonstrates how to bind and control the selected row index on SfDataGrid.

To achieve this, a bindable SelectedIndex property is exposed in the ViewModel. This property remains synchronized with the grid’s current selection and also updates the grid when its value changes from the ViewModel, ensuring two-way communication between the UI and the data layer.

## Xaml#:

```xml
<sfgrid:SfDataGrid x:Name="dataGrid"
                    ItemsSource="{Binding State}" 
                    NavigationMode="Cell"
                    ColumnSizer="Auto"
                    SelectedIndex="{Binding SelectedIndex}"
                    SelectionMode="Multiple"
                    AutoGenerateColumns="True">
</sfgrid:SfDataGrid>
```

## C#:

```C#
class ViewModel : INotifyPropertyChanged
{
    public int SelectedIndex
    {

        get
        {
            return selectedIndex;
        }
        set
        {
            selectedIndex = value;OnPropertyChanged(nameof(SelectedIndex));
        }
    }
}
```