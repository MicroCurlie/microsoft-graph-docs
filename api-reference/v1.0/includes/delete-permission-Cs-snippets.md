
```Cs

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Me.Drive.Items["{item-id}"].Permissions["{perm-id}"]
	.Request()
	.DeleteAsync();

```