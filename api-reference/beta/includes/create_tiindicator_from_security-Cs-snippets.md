
```Cs

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var tagsList = new List<String>();

var malwareFamilyNamesList = new List<String>();

var killChainList = new List<String>();

var activityGroupNamesList = new List<String>();

var tiIndicator = new TiIndicator
{
	Action = TiAction.Alert,
	ActivityGroupNames = activityGroupNamesList,
	Confidence = 0,
	Description = "This is a canary indicator for demo purpose. Take no action on any observables set in this indicator.",
	ExpirationDateTime = "2019-03-02T00:43:37.5031462+03:00",
	ExternalId = "Test--8586509942679764298MS501",
	FileHashType = FileHashType.Sha256,
	FileHashValue = "aa64428647b57bf51524d1756b2ed746e5a3f31b67cf7fe5b5d8a9daf07ca313",
	KillChain = killChainList,
	MalwareFamilyNames = malwareFamilyNamesList,
	Severity = 0,
	Tags = tagsList,
	TargetProduct = "Azure Sentinel",
	ThreatType = "WatchList",
	TlpLevel = TlpLevel.Green,
};

await graphClient.Security.TiIndicators
	.Request()
	.AddAsync(tiIndicator);

```