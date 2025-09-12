**[View document in Syncfusion .NET MAUI Knowledge Base](https://www.syncfusion.com/kb/13166/how-to-add-a-rounded-corner-for-net-maui-listview-sflistview-items)**

## Sample

```xaml
<listView:SfListView x:Name="listView" ItemSize="80" BackgroundColor="#dfe0df" ItemsSource="{Binding ContactsInfo}" >
    <listView:SfListView.ItemTemplate>
        <DataTemplate>
            <Frame x:Name="frame" CornerRadius="10" Margin="10" Padding="0" HasShadow="False">
                <Grid Padding="10,5,0,0" >
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="*"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <code>
                    . . .
                    . . .
                    <code>
                </Grid>
            </Frame>
        </DataTemplate>
    </listView:SfListView.ItemTemplate>
</listView:SfListView>

ViewModel.cs:

public ObservableCollection<Contacts> ContactsInfo { get; set; }

public ContactsViewModel()
{
    GenerateInfo();
}

internal void GenerateInfo()
{
    ContactsInfo = new ObservableCollection<Contacts>();

    Random r = new Random();
    for (int i = 0; i < 30; i++)
    {
        var contact = new Contacts(CustomerNames[i], r.Next(720, 799).ToString() + " - " + r.Next(3010, 3999).ToString());
        contact.ContactType = contactType[r.Next(0, 4)];
        ContactsInfo.Add(contact);
    }
}
```
