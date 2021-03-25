# API Notes

## Newscatcher (via RapidAPI)

```powershell
$headers=@{}
$headers.Add("x-rapidapi-key", (Get-Secret newscatcher))
$headers.Add("x-rapidapi-host", "newscatcher.p.rapidapi.com")
$response = Invoke-RestMethod -Uri 'https://newscatcher.p.rapidapi.com/v1/sources?lang=en' -Method GET -Headers $headers
```

This returns a PS Custom Object with the following structure

```text
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
articles    NoteProperty Object[] articles=System.Object[]
status      NoteProperty string status=ok
user_input  NoteProperty System.Management.Automation.PSCustomObject user_input=@{lang=en; country=; topic=; media=True}
```

The article property object contains the following

```text
   TypeName: System.Management.Automation.PSCustomObject

Name           MemberType   Definition
----           ----------   ----------
Equals         Method       bool Equals(System.Object obj)
GetHashCode    Method       int GetHashCode()
GetType        Method       type GetType()
ToString       Method       string ToString()
author         NoteProperty string author=Alex Winter
clean_url      NoteProperty string clean_url=thesun.co.uk
country        NoteProperty string country=GB
language       NoteProperty string language=en
link           NoteProperty string link=https://www.thesun.co.uk/news/14453072/can-visit-garden-lockdown-eases-indoors-loo/
media          NoteProperty string media=https://www.thesun.co.uk/wp-content/uploads/2021/03/comp-sc-rule-of-six.jpg?strip=all&quality=100&w=1200&h=800&crop=1
media_content  NoteProperty object media_content=null
published_date NoteProperty string published_date=2021-03-25 14:07:59
rank           NoteProperty string rank=436
rights         NoteProperty string rights=thesun.co.uk
summary        NoteProperty string summary=BRITS can visit family and friends in private gardens when lockdown eases on Monday - and they can go inside to use the loo too. The Prime Minister is ditching ...
title          NoteProperty string title=You CAN visit your pal or family's garden when lockdown eases on Monday & you nip indoors to use the loo
topic          NoteProperty string topic=news
_id            NoteProperty string _id=ba169c1691830b7e1ef1ccdf65fe584f
```
