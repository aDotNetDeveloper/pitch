---?image=/img/background.png&size=cover&opacity=20

---?color=#000000
## The do's & dont's of 
### A multilingual site using a CMS

@ul
 - Structuring your content for more than one language
 - Ensuring adding another language wont kill your team
 - Everything in another language is optional
@ulend

+++?color=#000000
## What this isn't about is

@ul
 - Google Translation Services & APIs
 - Amazon Translate
 - In browser translation
@ulend

---
## Multilingual Content

+++?color=#000000
### Most CMS implementions are like this

---?image=img/dual-language-site1.png&size=contain&transition=none

---?image=img/dual-language-site2.png&size=contain&transition=none

---?image=img/dual-language-site3.png&size=contain&transition=none

+++?color=#000000
### Instead horizontal content replication

![Logo](img/dual-language-site.png)

    Which means what?

---?color=#000000
## Multilingual Text

+++?color=#000000
### Dictionary Based Content
![Logo](img/dictionary.png)


+++?color=#000000
### In Code
Use of dicionary for in code every piece of text
```
@inherits UmbracoViewPage<ContentModels.Page>
@{
    var close = Model.GetDictionaryValue("close", formatOption: ContentModels.DictionaryFormatOption.ProperCase);

    var telephone = Model.GetDictionaryValue("telephone", formatOption: ContentModels.DictionaryFormatOption.ProperCase);

    var search = Model.GetDictionaryValue("search", formatOption: ContentModels.DictionaryFormatOption.ProperCase);
}

    <ul class="Header-nav list-inline">
        @foreach (var menuItem in menuItems.Where(m => m.Visible))
        {
            var menuName = Model.GetDictionaryValue(menuItem.Name);

            <li @(menuItem.Active ? "class=Header-link active" : "class=Header-link")><a title="@menuName" href="@menuItem.Url">@menuName</a></li>
        }
    </ul>

```
@[1-8] @[9-17]

+++?color=#000000
## The End


