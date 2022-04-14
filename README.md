# What Is Vega-Lite? And What Is Vega?
Vega and Vega-Lite are open-source data visualization tools that enable you to create, save, and share interactive visualizations. Vega and Vega-Lite are known as visualization grammars or grammars of graphics as they provide a *declarative* syntax to describe the visual appearance and interactive behavior of a visualization. Similar in spirit to how SQL provides a language for expressing database queries, Vega and Vega-Lite provide a declarative language in a JSON (JavaScript Object Notation) format for describing visualizations. These descriptions are defined as Vega/Vega-Lite specifications.

Vega-Lite is built on top of Vega and provides a more concise visualization grammar to build a wide range of statistical visualizations *quickly* while offering control to override defaults and customize various parts of a visualization. 

> *Vega-Lite is a high-level grammar of graphics that enables you to describe an interactive visualization (in other words, define a Vega-Lite specification) in a JSON format.*

Vega-Lite specifications describe visualizations as encoding mappings from data to properties (e.g., position, size, color, etc.) of graphical marks (e.g., points, circles, bars, etc.). The Vega-Lite compiler automatically produces visualization components, including axes, legends, and scales. It determines the default properties of these components based on a set of carefully designed rules. This approach is what makes Vega-Lite specifications to be concise and suitable for quick visualization authoring. 

Vega-Lite supports data analysis, data transformations (e.g., aggregation, binning, filtering, sorting), visual transformations (e.g., stacking, faceting), flexible combinations of charts, and interactions (e.g., zooming, selection).

As Vega-Lite can compile its specifications to Vega specifications, users may use Vega-Lite as the *primary* visualization tool and transition to use the lower-level grammar of graphics, Vega, for advanced use cases if needed.
<br />
<br />

# Vega-Lite Ecosysytem
The Vega-Lite [ecosystem](https://vega.github.io/vega-lite/ecosystem.html) is huge, and there are many integrations, applications, and extensions of the Vega-Lite language and compiler. Here's a quick overview of *some* of the tools that you can use to write Vega-Lite specifications: 
- You can use the [Vega online editor](https://vega.github.io/editor/#/custom/vega-lite) to replicate graphics from the [example gallery](https://vega.github.io/vega-lite/examples/) and make small changes. It's very useful for learning and experimenting without the need to install anything. Including data [inline](https://vega.github.io/vega-lite/docs/data.html#inline) in the online editor is okay for small datasets; but if your data is large, the editor would have to do a lot more work slowing everything down. Uploading data somewhere and accessing it via a [URL](https://vega.github.io/vega-lite/docs/data.html#url) is another option but can be slower for large datasets, and you will not want to make your sensitive data publicly available.
- To overcome the limitations of the online editor, you can use VS Code + the [Vega Viewer extension](https://github.com/RandomFractals/vscode-vega-viewer) to work on Vega-Lite projects locally. The Vega Viewer extension provides language support, interactive preview of Vega/Vega-Lite graphs, and allows you to work with local files (more details [here](https://github.com/RandomFractals/vscode-vega-viewer)). Additionally, you get all VS Code features.
- If you're authoring Power BI reports, you can use the Power BI custom visual, [Deneb](https://deneb-viz.github.io/), to write Vega-Lite specs in Power BI and benefit from the power of both tools. One Deneb-only feature I like is the ability to use zoom controls to zoom in and out in the preview area. This is very useful when working with large graphs.
- If you prefer working with Python instead of the JSON-based Vega-Lite language, you can use [Altair](https://altair-viz.github.io/), which is a declarative statistical visualization library for Python. Altair provides a friendly Python API that generates Vega-Lite specifications in JSON format. Environments such as Jupyter Notebooks, JupyterLab, and Colab can then take this specification and render it directly in the web browser.
<br />

# My Vega-Lite Experimentations
I use the online editor, VS Code, and Deneb. For each visualization, I'll add the following JSON files (if possible):
1. ```filename-online-editor.json``` for working in the online editor.
2. ```filename.vl.json``` for working in VS Code locally. 
3. ```filename-deneb.json``` for importing a Deneb template to Power BI. **Deneb templates are placed in a [separate directory](https://github.com/shadfrigui/vega-lite/tree/main/deneb-templates).**
<br />

## W.E.B Du Bois Challenge 2022 - Graph 3
My first Vega-Lite exploration was recreating a W.E.B Du Bois [graphic](https://github.com/ajstarks/dubois-data-portraits/tree/master/challenge/2022/challenge03), which was part of the [Du Bois Visualization Challenge: 2022](https://github.com/ajstarks/dubois-data-portraits/tree/master/challenge/2022). I used VS Code as I can't add TOPOJSON files to the Power BI custom visual, Deneb. There are workarounds, but I prefer working with VS Code for [geoshape](https://vega.github.io/vega-lite/docs/geoshape.html)-based, Vega-Lite experimentations as it is quicker to pass in local files. [Open the graph in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4IgJAzgxgFgpgWwIYgFwhgF0wBwqgegIDc4BzJAOjIEtMYBXAI0poHsDp5kTykBaADZ04JAKyUAVhDYA7EABoQxKHKhJMaANqgA7jQAm9NADYxABiXwaZLGgAcAdkshMdQXDShMcAB6bULRAAJQBRABkAQQAVAEkANVCAAgA5UIBxYIB5JIAFLNyAVSi4rJSkrIAxJOiACWSAZWiY0IaK6rrQxRBClNjo0IARJKaWhsoQAF0lADM5AJAEOTYIHCQoT1n5hpoAL09UAGYAJgBfJQMNFFRQBgAnQTQQS8wkAgYIfgBGcwQpGXkWzuyAC3gAnjgDq42Dg2NI5N0ZnANPcoRBXj4ICBTudXHckLIIHNgdpQII2GwANYMHBPQyIu5sBBeZ5XFnEJCCBhwLGBUD01BfJTojRQyKCJBMJDIboinxJSVMO5wYg0DTseToSLhbqwnAMCVuBHoEzmSxm8xJfhJRwWBQW7EKfkGNBfY7CjFQyrku6GFAe0UKphKlVqo2akCVHVKPUG9XGkA-c1mq1JY5m+1mx3OtBiAM+J6RO6UgkQJBY-NwIMh1XxiORYK6mFx8NPQ4Zi2pizJ8zZkACkyVp4AYU5NGJsjVss91eVtdb6GHkSb+sNGqeP0zlutxzzDvOOdQAE4h4u5LI4FA3FAGJpK7PQ3WR9EVy31+hN52d3uswf+y7BRPEA5ShWI2F0f1gJnRU5zDd8QFiZcY2bNcE0-FNvy3PsBQAFlPEAiz2ORIJAh953gyIAC1X1QiNekGUJglTdDez-AV7Hw4c2B9JADDYadAxgx8FxAYcshop90HoxjmJ7bCAK+QcoNFJ5YkuGB+PvITyITWJBgkkTpKY60WPk10XBAp5BjgCUIOVAT5W0uCEwYgz4N3LcuzktiFMOfD0jgNg7loEjoODWDJJAdIkJAWNaKeW0e1SDJslaJJIhSYYskSRsfNdRx8NiQRhFkNgaArZTHPC4T4NiaNYpQyK7S-JIkywvLBQ4yrQNkAw1VkULBOqnSI1iFI3ITDyWua38nX-NB03wgBpUtywcqsnMipaGgmiMpowpIZtYuaBWOIVuqeJa4FkTAGCgSkwXWsjnIjJaAE1dqedMkutdtvJOgDjndC70HCNgGHK-rBqqmsXqeKJPvQbtPOtU1-sPDyQZAABZcsy1gD44GwCrSM2kTsZiuLIpY1N9uOjG8Kx3G7jBCVeqesn4Ox-TkNXSLvpRpI-vagGFr8pmkBoC8OeGuH0GxrpebfBMjNkkWMaUyz5ZoWAbAJGXYci7HYkRxMfrTH96fm1BjgKpmpYvGRXgNiLyfGpX4qkzKZJM9HreOICtZx8qZHuGgXZqhNsfEj3qY7A6Bf3UWba6oPsZDjOcBwcOtNlo2dtjkS0cFxL1et9t8Ox+YCWhja8-Jl9C-g1XfbLgVDjtoOUiC+gklHRkStr57IpSYdTeRlri6Tw9DlTz0nm7u5e8GJBKTYZ3c8NkTMtNlvWr99vzq7uAlXLEsI5GhfFYavnDO94z97bgDDnF4-dCSWppTwGAaHszfXfgikWou975q2nuXYGx8OSXAvnLEAKR4ggIYg-UyHVDiMzfkkAAUnAO4EA4CPX-pHCMKQsGmzpl5J+aBDh5ixikOA79sZ+B1ppbqw9t7YyQT7R+4D26a3nugeh783pBUpLAkeH0m4JiOrJA+z9A4CJAFkH+rDSb13glkYBUiIwyN9nItAOELKKKyJSCUGkZREMvugLIS0uEoP0agHCR9jHKjIAiSxcCsiNm0U8PeqDk44UgYo3I11CSsw5JOIenMEy5Epo1ESbUWqJ1moeHCGDFHBA0gYKssQIBsxdB4yKwQTY+K9sgsBKTrY4VoUHBo4Ne7924lLKJ6iEwNDHqUkAU8Dql14QBHC-CVLoDqbeGASQV5rw3mw6JEYGg8xvsrOioDW59IMZ3RR0RQk8nwZsaZrSIzRHdgsz2IBhbTXjlbXCc8hkgE2b4NahSRLRAABqmzOQdCelTcIKJuYUV4MBxGGUbscyKfiHFiGcTc+Iv9aCRMBfBeIcTb7wW6duG0R0zKoDtFjeIuClg3XhQmeIwKqZ33KSsr5AExCv0UQAdXLD-WQZBMDuL2VveCtKkWLN8csnhlLczpJubSnkmAkjQuClLKcjyOWIM6RQ60GKOpiBqXS8qqhCRS0JRGWlJSQVku4f4w8YhBkFnQLSsETIpZkC1U8Wlki9XN15agyYuJKQELpAUkAMwaA2QMLyIIlkfEur-N6wQPg7gslKqCL1PrBAAXmkoOQcAsgzG0O6L4QovhiGDacaYiwkDFhZJgCEUIyCBQgDAJAkJHQgGuqoPqTKWSqB9Cyb1vqnikvXEoYt1b0ClQQM0x4wp1AeBZHxZAmrAggF6SmNImQshpQyllHK3RUWphnb2JQny0Wou6O8tF27ujJLRfu7oiSE4XO6Lo-ecklDysOres2gs6bdDBVhPN+ImUHCCAAYgzUmDpIAf1HnMI4AAQiYRw3RgNfHsGIRwXxoMmHQfYE40HDgmFg2II80Hhw4UiGIew18f2DBOGINJ0HBiDEiCYI8YHoOhDEJEQxJhKOHGHIcSIy5g3dopGGmgtI+QxvbegQNrgS1PH7YO7obhMCjuGfPENsb42dtZT2qEUmBpDtcO4KEuR4nrlzTiOasn5OgAML4NA-B7AuAMI9QU2KCSwCCk8EUS8ZN+ACL+wYDAwNlQgMOStxVrplvTEDbo6R8Q4B-lAVASQAACFbeIzF9GQCGUwtgEuGeQNgVZCi6rmDdHY+xXTi0K5gYVNg7DoGELYcN3QSpwFqHAKrAR0y4mQIW9APh-DYjzeq711qbixV4g2ob3gYTUJcEwdeLLmSChcB4GYARsWpeqxYXEUp7pkEZAwdm6ASOhGHJUMDlQGvkGugBUAQUfVZZAKVaWSgPBlt6q81AZgnsXd6h9d7zglDNoYAgQkC1-vcUB7IXIo2rUOBcIyXQkODBjam8KMECAZuCGiBJ0TABHBgBbdkQFR+j4rBwbMWSJ9xBomBGRutpYYYwqBzCUFoRKJgNkU0zHwQETcIBWc2UqPMJ4qgw64KSBeXQDXJT8+2HsA4WantS8EOEGgA62vYtMwcWQBpBC4jLSsStvbQDohp1CJgEp7rThN3TowALGfM9xDgRkkhLwLnBL2kAnI2d4MKGWbEOIgA).

<p align="center">
  <img src="https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/du-bois-challenge-2022/images/resized-graphs/graph-3-original-resized.jpg" />   <img src="https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/du-bois-challenge-2022/images/resized-graphs/graph-3-recreated-resized.png" />
</p>
<br />

## Black American Population in the U.S.
I wanted to experiment more with Vega-Lite's geoshape mark and decided to do a choropleth map with a dark background. Choropleth maps are great for showing the big picture and helping readers recognize patterns in the data. You can easily see that the highest concentration of Black Americans (alone) population is in the South. I added tooltips to help readers access exact values for each county. I used VS Code.

![](https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/2020-us-black-population/images/2020-us-black-population.png)

##### Note
In 2015, Shannon County, South Dakota (FIPS 46113) was renamed Oglala Lakota County (FIPS 46102). The [2020-us-black-population-data](https://github.com/shadfrigui/vega-lite/blob/b7cb5cd2d4ccffe43612b2485d80965b7d231f31/2020-us-black-population/2020-us-black-population-data.csv) has this change reflected whereas the TOPOJSON file, [us-10m.json](https://github.com/shadfrigui/vega-lite/blob/b7cb5cd2d4ccffe43612b2485d80965b7d231f31/2020-us-black-population/us-10m.json), has not. I replaced the FIPS code 46102 with the old one, 46113, in the population data.
<br />
<br />

## Premier League 2021-22 Current vs Predicted End-of-Seasons-Positions
The following graphic shows current vs predicted end-of-season Premier League positions. [Open the graph in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4IgJAzgxgFgpgWwIYgFwhgF0wBwqgegIDc4BzJAOjIEtMYBXAI0poHsDp5kTykBaADZ04JAKyUAVhDYA7EABoQAdxoATemgDsABh1L4NMlm16lapJhSpQxJIIZwIaANqgAKnCQI0IALJIsgAEAMJ0AJ6KICEMAE6xcLKYaACMSgAKCWo0UJjs8qgpAL4KHl4+6AAyNKSxOGxsglEx8YnJqABMGVk5eXJoHSVl3r4h8IIQXs1xCUloAMzdcNm5+QtDIJ4j6ACCsZOy9tOtc6gALEsrfQVaG1sV-oFBAKqyImrHs+1il71r53dyr4AOpOTBBAASIyULS+aAAbL9Vv1UABOQHbTZsbCJGDQ6IzNraJHXBEYh7AxqkZwwwmnAAcJP+KUGpU2QPQAGU2Ax6N4cJh+rSTu1UUyUSl5uTRrFwhArIIgul7EgoHBPkTCvoQJlln8JWJpbt5XIggA1GiCQQoYVwwppHU9ZEFelGkCVOA5MFwWIa04s8UFQ1s+6+ABCsSMWCFBJFqUWjr1ztS8LdADk4MooEh5YJ1bbNSkLomrsyzm6I20AGZsWIfAv+n4l-UFFLokMc91wZY02N2lKI5vJ+1ugCitUF8gb7RSWkDqR0FbisjzkWnqUZQ9JhVdHcxwMsNbrfpnYq3-w6i73DzTtdUsBPA21utLEtuAF0SiBElA2NlZGQaCgAAHkBIBVjQcCCB86ChkomDhDg6roLIbAIDQhxNEoMixO0oAQVBMF9kSRSkUo1rhD6rigMgsQANZgQhSG+EwSC+kov6CLWYFwMBOC+ugFiYAwCAuAA5LCbRie+QQADxBEJIniS+LbSUEAD8QRiQAxAAYvMZxFvCYlBKgWnafSKQhEWuliSAZHfrIv7-oBNggJEbkEdBox0sk8GIchIAAI4MIEeRWHkpBRDh7QgGoThqrILn2Uo4QdGBXlESpyakRstEMW5TGBVANCxFAebRTQABeyFiGYICcdxbm8fxviKaJEm+Wp8ntcpTrXGpmk6fphlnMZpnmZZ1lnLZ9lfj+f4Ya5oAefhkHeeg2Wkv5zHoCFYV0JYNTqrlbL5YxAW+CVZUVdh1XIfC9WNQJIDafMAAibZiGGKWOc5S1gat4HrURklzDtgX7Ukh2RSdZE0WxBWgEVviYLxfnuQA8lWVaTHh358S9vWdSK3UKZYSliVt+SDUEKQTTov01kknL3akXQNY0TWgC1RMUx1YOYGTxPU3ItNicoMAiCZZliUw1pQHRdkOQtyVuUDmW+KLU4gCje2hdDEXHb9aPAfjmubf1aynQj9EXbtuvo1EzOYKzNXxhxXMvZLIi-arAPqxlIM+XGEO+FD4VHVFX6m+bwfoILc1FO+nuyBBy0gDgSBqGryNsDgaB1UoTDYoKFRFyAeZVu0l5KJGxg11eICsYrZCxDySW+D7aNRMQkHKGB8rt3RgWYLEgQQFncJfi7vicuQbBwC8ACSURIMBNAQAAGmBtaQacuv51EbfqGgY+OEoJ9qJjWclQhqTmGhSAYWgVb2JM8E5HRzioG-ExwORJATAoLKhzgHWulcgFQV0nIV2bNCgJnChVVAsgGBWi-OvTeABNMC2QIBAOQefOAX5WICVAKoDQMBUjBgaqVcqyFQD51VBEVIuUgA).

<p align="center">
  <img src="https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/premier-league-predictions/images/premier-league-predictions-online-editor.png" />
</p>

I increased the ```labelPadding``` property for the X-axis to make room for a Power BI matrix visual. Here's the final graphic:

![](https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/premier-league-predictions/images/premier-league-predictions-power-bi.png)

If you want to import the graph to Power BI, check the [deneb-templates](https://github.com/shadfrigui/vega-lite/tree/main/deneb-templates) directory for more details.
<br />
<br />

## W.E.B Du Bois Challenge 2022 - Graph 7
Since I started exploring Vega-Lite, I quickly realized that recreating visuals is the best way to learn. So I decided to recreate W.E.B Du Bois Challenge [N°7](https://github.com/ajstarks/dubois-data-portraits/tree/master/challenge/2022/challenge07). [Open the graph in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4IgJAzgxgFgpgWwIYgFwhgF0wBwqgegIDc4BzJAOjIEtMYBXAI0poHsDp5kTykBaADZ04JAKyUAVhDYA7EABoQAEySYUqUMSSCGcCGgDaoAOJxZyuACc0IALI64ikAEEycAAQmrbBjlsADPwAjGLODlZ0Oh4AyuqYDAboMTSyZIJOSgAK1lDm6u5owQEBSnYxAJIAIkUAvgqm5pY26A4Zzm6e3r7+6KH8AEwB4UiR6oKx8Ym2KWnt2bn5SIWoAJyrlGJllTWowfWNFta2bZmu7l4+foEhYWWjURNxatOto5Fwys45VnmyBU5UKV7Ds0AMDiAzEcWvZHB0Lt1ruggqERmNos8EkkQAB1GjKNgAd0+30W-2WgOB5WqaAAzBCoc0TnClJ1Lj1bP0hmjHpMXtiIh8vgtfksVgFNtsaahwQ1IU1jm95uculdeiAucN7uinlNsXiCcThSAfn8AWgqaDUPS5YzFbDlWzEeqhoM7rCdXysTNUukzqaxYCAGwADilu32toVMNO8NVHPQroG7oivMxrw9QtJovJK1pwUlIOlssOTKVZydatsSZTD3GXozBqJJJFZopFsL1N2NtL9tjrIRVcTYn4tK1HrTep9c39ZPN1st0sjvZjLJV7KRIGTo-Hqfr6YF7xoLZNc-bqCDq3DYIZ0eZjsHCa3I7HPP3U-QTaN2bbK2C1+tW9oXvCtH03MdR1rT0D2nP0f0DMFFwjICywdUD43AoJaSgyd+WZKws1bBDUAAdjDItdhLeVgPLOMN3VCDsLfDEP1xfFm2NANc0BAYAJ7ajUP7ddnVsbD+AAFhw988OSX1lS4+dyK7OooxotC6JE9AxMk5jdRkzNj04s8VhDIMAKou1VwfDCGJHHTtVw71P3Y78iO4tAzIoukUL7NdKyfST+DEKSWP02Y4Lc+dPOUvYfKs9D6NsQLgt0htDwIwz4Pc1BTPMuKQI0ocQGSkK9KctjDRPBTzyUq1+MsgqBxs2xgv4INSrS2D5OMwFxIA5cBN86zEvQVr2tSmC3gyqqerQEMti8mV8topqRpAMaOsmiqOKy+dgn-Rb6rvFbhKKgB5UgrA8caHOk8rwu6nN5z6xaBoak7-M3C7rGuzbWMFTLIvPEjoqtCzjvU1bNJAb6rpuic7sbFyZqe88hj45aQAAMUQPywPVFE-rCuTZ1Rv8Sn6zGceQYbocJib-qPFHf0pPLVNQ6m8ea5FbgZ-Sv2Z4ikO89n7U52mis1Pn7pJ3aapemK3oh8WEuhqXbtC8qAcF7LglB4sqdxiWn3VhHNaRyqjLJ1nDsNmnVaKmtpYzB7SZZulaqXO2ubWp2NbKjNtat93UDET3KO943Nz9s2A-1ZHg+IhW6sjh2n23V9-c62SZzlv9w5UldbBVwr05fXc63N9LCNPa20BI5ODdFmES6hx3y+d+PLbzwEC8A5vi6NtPMMgzuurd4jgl417U9LkemKzrag57+u+-BtTW9Op9GKJ8qBcT3Xhf7ov0E3z7bIk3eXdloGTMpgfT6HueL-s2Ps4MnX5xBtmT+xp+2+3nZK+Xcdq30BHrDGD8-722fklEcKVF6sVdivC899f5n3xnAoKwD8I12qisIM+sI5QIwdzYq8CcHOW7mAsEfcjob3-lvTcG0x45wirXEOjdkIkMYefFqI54Z7irrgwGHDiJiGnjFdeHNeGYNGgIyh21XJiOyuJLhIt0GyLIbDX6rCQDIJoagdRsUeEwIAV9S6ujEH6WXoYscP9Boty0WtHRgjK5x1sPvFBhCMYAF16ggGIFAOQUA1BGFAISfE9B65iGBJgOg7RNAgEwHAAAHpgWwABhOQkgGAUAmMEiwdB2CyA8GwAAZh4FwCBrA0FCaUgAcuQHw+gPBICgMEqwyhfQeEwGwNpFwcC1LYMoCAlBnDlLkBk9A2SrAUBsEoSZ-wUgAC8eLTyWZgHEcAaBkCwLYYQeyUkLJABAZg8TMAZCyEgZQ3S0hggWmcpgFzEmGBANkop8S5AeEKbk-JnhLAQA8A0gAF2QKwrTqkAEvIj1KBUgBgHgcBsFSJgDwlgPDED0OizwggADkAAj9w4ylBVDkJ4JgABPKplykDkg8AAVVkDQS6EA6CUvGb4pQTyXlwCxlMrJbA5mjGcDyhJfKpmrPAY8854r+X-G2bs-Z6BDlYGONy2Vly4AABlUhwAABI7KOXSMQATkBWAANa2BSekkAEJCmhOmcYEAkTlDROtCRBa8AlXTM9XE8VaBQAVPKRAOA0z+BXmSWk6Z9gXDaoAKIxBJSATZthOiyCgNSrGAAhCZkqaBrKKKsAJggkCUsVM6zAVg6UQEmVYBA4SU00EEMcwNTa4CCC+OgBqSg4AAEcGA6AKrUWoXKQDmqtUkzAlKhm2CYCKgJ5hgl3LIG21JbbynHk7bYfBZxp2zvQAOulFy1AsrODIKwMbAV-BXc4JAqSaBJFAKWpgHazrlJDWGttaScAwlUAkBAlBtC6E8AAXlAx4YoAQPAAH4PBtQ8KgDwwwR0BMpRurdXamH+CUPuwEIAhV3KHdyoVV79A3t9KK0JiTQA4BuSuioshZCKgCAE+9j6228oABpoB3COpQwTBBCowx2rDylcMzvw4R1IxHTnUcBKAAkyBUhGH-LxWkY7q1pEBG8gAxCUcSVQXBBmcLpzJIYAjZtpCRUzwQsYhmTCZ-xSgMjuAsGgWQDBBCCFQ3Kf9GgtA6D0EkYwo6zWjEnaAPD1ro13tztaYouHYvJAqA0kwCa83-DTW5zNHgc2ZcwFKh5iypmKuNegJgbBO3HEXRmkZlGknrqScBvQYJxKsaUOh5rQXgzWd84ptQAXAk9ZC8AMLSgJ2cckzF21Sg6VwQS3E5LsaABKK2KjxpqCVrL6B025fy9twrBaeILU2WV5VIBKvVZsLV5dDXQBNcCyBoo7U0Ntpa4CWkkl+sqEG+9kb4Txvjoi1Ng9UbZsgHm4kgYqwlu2s-NUM6OJNsFey0urNubDtFZlMCM7RqLtXaZLd+r9zGv-eezKU1nXyetZyqakdzmIlRJgHST1ShvXlb9bhgNSTg2hvDZGm1MasbxrsHGxNybU27Zyxjgr2PgjFpc2WitUWtO1qFQ21AzrN0tsVKATdonbA9pAP2wdghB4wIZxNkHU7psVYXb2urt6ydJIN9u9Au7nDRcPYO-4UR4mkDvQ+p9IAX1vo-fz79qTf22H-QwQDH2PDgcgyUWDHgSKIeQ3a-jIAuv68w2jxKEmwfSdkLJi9ZHoBNEo9y+Tba6O3N9Ix5jLQOuQ+D22oVx4dsgEiMa7nWqeMLhz4J4TruC+tFBMXqTXSZPm9r3CJJSmkAqa12phQGmlBaZWHpgzRmTNKDMxZqzNnD92Yc2IJzJbyBNA815nz-GBvqBp-oQHzngeWtB-hoXcWFuxKS-DvoqlulvGqjtLujnlpjimvmoWpTodudjGoTjVo7ndqTg9i-kUGOG9t1hTkGNhD9v5i-qNkDpNrbmDj-nNvFv-uDjGmLmthtlttAT3ntrLljsdsVkwVsvjogVVkTigSTqui7k9rTkMG3nnsNhTl9qxo-r9s-jgcFm-uFp-mQd-rFpQQtiRHDjGjiIjsjowVLiqBmqwZwdjujJwQgXOrwcgSbk7vdiAI9hIbTl9lTrnhgXsLEqhv4ozskjzopk1rSEGCRAATGlkPGith4JkvGg0gACpJpgGGH7ZQGbLy5BhKGTo0F2pygc7KoLS8ptrKBNZBTAh0qwBj6nLqCXpe7JZ6ZVAMDZoooQCZIwA6AZDaZDADADDODeBIA4AwB1JIYAACEAzRyg5SfeDANAIAY6BhMQ5AbAngDKFQcu7BewtI8B3BByPq6qoeeqhqPqiEaRM2GSo6Amcgm6ghtG9GdhfSvQ7WLmcA5S0yZhfeyqQwAS86UAFq4Kvg7m6AumVQ2aVQwQmSnRc2HeSS4K+I2SQmMITApanxXudSFqSQ5SOgoaSur6gg8qMaLBkBzgYeWJpWGxFWVhN2YJj6XGAAir7iegHgpiAJCcoGdHRlAOylHjHugAABRx4J49YeAACkKeAAlEnhBtBnBhKLSJnhKMEJkT4Z8dkgwDttQQSdco3qTtPASfGtHjCNyS8LySBgKcKaKchmnjyUBnyUhniniviUgJidifLmsaHnaR2tCWPqAD+n+vqRaYacnuKR4NaZnninCe0hajaQEnkagJ5t5koCsqkJYE1pGO3o+gAJpVCPpQAQopJtqMloBVp6Dc6fHZp0pYbRr5DOCMnMntJslAiUBOmqlXGk6JbOmYnvqfrhpmEEkOkrEQI+FappomAS6IlaouDxb+paoplFAvS8rYlo5GF4kD4ZDdmwGhCLkSoKrEmXaknOBxlHCJkBIOphJJIQAskNYhCoZAA).

<p align="center">
  <img src="https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/du-bois-challenge-2022/images/resized-graphs/graph-7-original-resized.jpg" />   <img src="https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/du-bois-challenge-2022/images/resized-graphs/graph-7-recreated-resized.png" />
</p>
<br />

## Monthly Variance Analysis
The following graphic shows monthly actuals and forecasts in a lipstick column chart along with the variance in a column chart. The code is optimized to show millions/billions in the Y-axis as well as in the tooltip. [Open the graph in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4IgJAzgxgFgpgWwIYgFwhgF0wBwqgegIDc4BzJAOjIEtMYBXAI0poHsDp5kTykBaADZ04JAKyUAVhDYA7EABoQAEySYUqUMSSCGcCGgDaoALJz6aEACkk8pWdn0ABADkGCJnABOaAIxKAMTYvOCgkCEw0ACYAFl8ADgA2AGYUyiixJQBBKEwGHT8AdjF4koAGGMoY+KUANSQvGlsoOCcABW8WxyQyODR+MvTCqIBOAF8FU3MYSwC4JkUQB2c3D29owODQ8MjUKLKysULEqPj0xOzc-ME-EcT4kZiR3yq6hqbZFvbOuG7e-sGZQSMQmU0cM3QJgai2WMFc7k8PlQyU2ITCEWivixUUKD0oNRAOTyBT2vkSiTJJUoKJA9UazVaHS8XXU-1QgKiiVBS2mliyOB89mm8LWSJiqO2GL2h2KZTulEShUuxJuqF8IxGcuS1QVUTe9M+jJ+fz6qAGlDKyVi3NhlihAE8YcLVoi0JkQEE0TtbjExIrCoVKHdlddMSNkskjlF0v5ae8Gd9mb9WabBr4cckbbz0FYGHYeeCRa7UBcPVt0bt9o94tVA7GiaG9vtUuGRgrxXGDV8mSyeqmLWIolnwZZczchYWXetUEqy16pftcSlFek9YSriSogkgXczgl9R9u8aU2hAdVxpMCxZ0FkGGQnZOEdOCZ7Jbt1WV4gHLZRCh2G5uhw1qcgZAgeCY9smfanhauIgpetroAAynAOAPisT5IiMEoVrcowHJyQb1huqpbjEiRiCMX4KthnaHkaSYmjB2LxMO14gAA8rk6FwlOSK+GUOHemqjwxKM8TRvEBIAaRn6JI8ySDMkBJ0vRia9mygKFNqbEQiALhsMQPFFtOWJCVKCQjCU2nJOktEyZi8S+DEf5tuS4GGupUGaZQvhiGUXIIdmIAACKhMZfF+Gur64SJymxE8VSlg5exOcMvptp+HlHoxJ7slUYiRmMAC6EwgJgXi2BAABmwQIEYoBhIIUAMIIaimiAIQ4G1LQABS1V4yCYL1qh5AghgAOQyRNxUKE4E3pBAE0AJRzRNADiE1rQAQitizhHyJEACpsGwgiYDQaHck1LVtZgHVdT1cD9XVagjWo7iTTFOwzWti0rWtm07XtSgHeg30RCdZ0XVds0gMQUByGEuzGCAADuNDKNeiQHEo8A0GQWDRLjIC-Ijyg0LI96aCAAAeaCgNVNBwIIyh2rySiYPaOAdbIbAIJTBRKDIXi7IzzOs+zj6iosbBoegEDuCAZVILTNAGDTwTM44liYHLytlY6NNMyzbPoKpEHHtBnPcx1ACO+SOHQag0KQ+1qxrjOvbsIC+QApIsZCNMoADCZ3BAzpO0wKlije4lDaLorQALzJ04ZROAA-PNADEIVRCHWQh74E1OKg80TcrShtZ4ghh4IEfoAbZVtfa06o8gXgANaR1zPOWEw0JKBjWMQn5SiIw3SKgHA0dIioH3jRNFueZBJozU4AB86dZ7nUTbUkIfJKX5cTXn22JFk8S7c3l6dz3NN9w9oSREo9ocdV1UQHAYtRzH6BxyXivHKGk4Ab23hnbO-A-JlycH5W+oB7691trrWer8QDv0-t-X+s9-4LzGpNYBDFQHgJ3lA5ysCyQGyUGTNgFMqa9zQZHE2ktzbxlXlbf4SgBpDUsP7ZupVLwj2xiTfGhNKz+RoZ8OhlNqagHpsbCWZsrwzBtv3dAfMBayCFiAEWv8WHKNhCZHwYxDaR1VurZh3s+FRAMNXJAtcACic9LCPSQH1QBlAa4s0Blteau1lqB2DvXRuIA84FyLr4IJmMOI4HcXQI2gx3TeLruHaef956eMTnoJwqcyEV1gWfHGYhHFiBDpXUxZVJ6N1AIA2Y5ZvTCyaqaWp-MkCUyMHON8iwHJKDaGwCATgiGLBcOQIZ7CWggDhpVKmppDBhPzoXYuiwc6+EcTERxUkVn70PskFZIUL5X22lMyp9i25Ig7g0B+oAn4DyHujTG15FJlVofQuRGDmFKPqfOdBtz0AO1sBddQF03ZlT1tDS6DUQAGKlhYbkMLwYNMhqdc6kLOZ0EEB1CGkQSqmLvlc5B6iQCD0FA80efh3QRC8GwLuHU0YwBEIsKlNK4CxPiVzGChQXnSLeZHI24tTaHRVIsP5IAAVO2Ba7PoVS0mRzqTeEiVdyoophlChFKiq4CtYeuFUUNUVoXRZgTFQrQy4txXDRGsgmbvMHlALuQc2B5mUTnAIji3WOLKIsYgzM0aR2ZbS3WMyIBxJCDrMqtUdbIXIGwVoABVAAku7SxNMUlBEcEhGgAAvU0ZlyoYtNLIVqggVYewABpyraZTEJ89wlLKiUoIOmM0DVR0N-dFdrq2WFrZExYKSshU2Neyextc2hIGULy1AySHEs07egHOxTSkhyVRYiAJ15agDYFgn+0QxAlvVttNg2B+a9xoHa7athlFoOTCK09XcM3Zr8GUPdEAACakctbXvQI0cRixlCVvkKgFtgg215rtRrIDIGLodsdZGqdI6x0ToEi3cgvwzYbsaJ+kAfNZB9CUBTNEF05CWBgFrTN5gdGYt6LIZQ5aRKCRAJR1Db7pT0YgPaDwZ0jooIVgCkITL2NMDOvenN+xhYCaExVFls7ypBpDde4dLM02YGE34WMKTpM5xiBGCS8QlUkt7iqyFqAKp6DKgRyOwiISRjxnAAmRM1SzkRl4HDXgABKY6aAMA1h2f1HV52HEXUyyTtKADqjyIRKQnrKpuYKmE02qTWrT8VdPcPMCptUvgZWfDUH6uJUBZFoBiE+0xQA). 

<p align="center">
  <img src="https://github.com/shadfrigui/vega-lite/blob/4a7c8b59f3867361f84999853f971b5b8aeb629f/monthly-variance-analysis/images/monthly-variance-analysis.png" />
</p>

If you want to import the graph to Power BI, check the [deneb-templates](https://github.com/shadfrigui/vega-lite/tree/main/deneb-templates) directory for more details.
<br />
<br />

## Box Office vs Gaming Revenues
This time, I decided to recreate a [Financial Times' graphic](https://twitter.com/ftdata/status/1484890343086637058). [Open the graph in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4IgJAzgxgFgpgWwIYgFwhgF0wBwqgegIDc4BzJAOjIEtMYBXAI0poHsDp5kTykBaADZ04JAKyUAVhDYA7EABoQxKHKhJMaANqgAJhpSpQxJIIZwI24AF8AutaXIATgGs0oTAE8ccNCCdwUJoOIHCyqro0smTuIAAesSZmvqj8YiGeiabmaACMABzWRQoedIIpoGwAZlUQcJqpuUqYcHENIAAq8AAExDS6cGzdFAhw3VG6DBCYTp7jEN2ybADu3VVITt2CG2Rwm-RIst30YwhsfWNMU1EWlkpVcpgAyjQAXikATE0gD7KYAOpwGhkLB+JZOZCCEAhVThDRWEDLfr0NAAFgA7AAGJTwYGg1CozHYkD6TCGYzZCwIgCacA2aA+mNyxIASnBSLIcqgPvlKKjUQA2AW5YUfVEOUC0+ncpnfNkcrkfACclCFH3RYlyzPFJRAUqcDKZHyU8rCXIAzB9KFqBejzbl0flzRK9XSDTLcuaTeyzSl7ZQnUqBUqMQL0rr9YbcqjvQq-ea+UGlUr0ejUeHJW6o2JY760OaBZRNVr1WIlbkXZGPQLc5y-YWxQUUw7ChGsx70bWLbyHZjUerMerK+3GQUu37eea+wKMUqecPpaOleP87z8oPNY6Bc624vB6yfXW0OjKErzRj+7bW5m918V6gCqqBU6sejcul7EowhEojEjPFYiqGg4EEXQ-EjZpvBSEAlgQKJTEUEBoFMCoQBwJBdEiaIAElZFkPY0ExShzXDEAkDiGhLH-bYmBAgBROIcHdEkNAYBBKCScxugAXm47pR0xboAH5ulJNiOMpbpulQY4nAYOEWgACjE9jOLgBR+IUABycoqkwLSNK0rSAEpEJokCAHkajqBpmSUczBAAMUePwAFkaCcGgkAQMykFopzHhed48gkdIMkA4DQL8U0j0gnw-AARwYQ5MDoDQaFIRDkPKWJdDYZAom0bEtUxT8yIoqi9HypBCtQdZBDqZoymggBxQQ2CYUxuiYNg4m6aogKgMYAjjBZFLAJhZFMprMHKAANNB+CnGbympfMwpCbZPAI1AdBAZw3H-Lx4vQTqDSUOIrNqeo8mJVR2uYgBiXIABExDEfIACFoRdA7YmO6CWjaRD7rYd1QFaJi-BUrQtJi8wtNsboAD5unNXkxGE7otOWGARC06Tsa06ELqumzbqUTwyZuh9iV+dp3M87zEPpoKUnfEJvzYLC-w8VoGlAICQLA9B4d8e4weQdpKA+H6XVJcllEpKidDsEI-qOqC-CBzRmn5vwnjYBgnCGmTPt67orpoIbulcthJDYABuboADk4GWV42DYFnArednjRAUGnoFTExDosQAGESdCcJud-WIEn-NS0BD8Kk8pNFCSKNXdSRXQUQfRkcSBEEGkJYkFayZIVdAJ5yFGP4-AjuQZBy+8xCInVa-rsIGY6mg25AMW0DPGWXTrsgG-aAAFKP7wLSh0RzmOf2iBOIuFg2e8buLoNg+CoSUGQnAFn5IpFofDxyJQwYGZiBmgMIecQtgcD8UZDmj7LUPQzDf1w-C7oiIkRCORSisQHLTwws-f8kN76sVUpJXi2Nm6yFbnAAmIlGSEzENHBy1NT5wOhggiSyQeJ8S0qg9BmD+KYxku+PBfkQLOT+GzPIVowqUw3lFUWV9xYgABolZKfw0qpUykfdQOV-x5QKvIXaxVmRlTAZVEk1UogvSQBAGA2gvQfFsEoGRNVZD-GRNoh8RZ7JMIamgeqjUBHNW0CAFq3lfzdBGr6O4IBGRfG6ONSapl9H2NmnAAAMjcAAEiXfEHwvRBPmseFacA1qoBAcUEAW0dp7Q1h4LWp16Sk2sjTDmX5Y4wNAEHbhF8J5TyypI1ChjapaBAFQtgg87ZMAHvw2eIBAlOEOLsRxz06L5EchHb6ShHohheh8OiApEKPU+uaS0YgXo9M2uQJ+aBOSCEENnXU2SBG5IEfrJQFT0C4xEIhS6hTbI5hAFTG5FMfguXQIzLyPkJasL9iFTmpT45HX1v+IWPDL5xh9hCeE6AZZy3sLC05cggK8xAJ1KALgyBOCNrIC+j1HJ0UcrkcOiFf5lPSXAPSIUlCeVLmgDuSgerYHyoaEIFxlixGmBilwKRtm7M+e0DoSAYDVUQsoha0i1FyNsepexqKqKSssf5AAgtEKRxJIHQP+XchyzcHp+EeiHMOkdEKpWCVshgOzQEVWSaAdF-RtVg1iEQ9AKlSFcQADx8SVIJESWlHrTIjgqiOuQCYySMtHG1ugLLoSgHQTIqAiJ3NSjKmxpg7Fqr-mvWm8rmEvJAG85mWaApfOCg+UKBa7Xg1CIxeBmBxJqW6O67onqsY+v1eHCOwaibR2NeUJVZAVWJIVcIMgcjSXksSSw543yS3jseICPE7RwSQiNc1cturW2GpCAEIIsQwbAUbugQVnlPZ-AQkoPOBcQ7F3nWiCxgdWn2tOtsVF0dYTqFPhAKN-zGTZyAA).

<p align="center">
  <img src="https://github.com/shadfrigui/vega-lite/blob/57987450644a3ebf0cd55130d7ad9e50f909c4c7/box-office-vs-gaming-revenues/images/box-office-vs-gaming-revenues-original.png" />   <img src="https://github.com/shadfrigui/vega-lite/blob/57987450644a3ebf0cd55130d7ad9e50f909c4c7/box-office-vs-gaming-revenues/images/box-office-vs-gaming-revenues-recreated.png" />
</p>
<br />

## 30 Day Chart Challenge 2022 - Day 12
Day 12  of the #30DayChartChallenge2022 was about The Economist theme. So I decided to recreate the following graphic originally created by The Economist in January 2022. I used the U.K. data. [Open the graph in the online editor](https://vega.github.io/editor/#/url/vega-lite/N4IgJAzgxgFgpgWwIYgFwhgF0wBwqgegIDc4BzJAOjIEtMYBXAI0poHsDp5kTykBaADZ04JAKyUAVhDYA7EABoQAEySYUqUMSSCGcCGgDaoAOJxZyuACc0IALI64ikAEEycAAQBJACJoAjEpuTugADM4ACmw4DIJq7LIeAEyhKWgAzABsof6pShFWbJJwUJgJyaHp4ajptf7pAOwAvgqm5pY26A6CTkHu3n6oSX0hIP6R0bHxchVpNQ1itcMgBUUlZTMpVRlZSQAsoS1tFta23b2u-b4ZI7ZJEzFxG4kpc+kAHACce5li+YXFUrlLbVdIHJZHEBmE6deyOZzBAZoPa3dDpB5TZ6zaoHfzvTIolYA9bAyqgvZ7dJ4yHQjpneEjJGoP6XUZ7DFPUlzPb+H5JBr-NZAzZkjJ7d7+JL+GntU5dBmspmZVEgMQc6YvVI4+qfRqCwFYkEZMT+TINQ6tKGy2HnBFXQYC1m2TLqw1a5GmiUs1YG0nbGqLPafaWW2lyuE9O2ea6od4qhqurk4pJiBaffUkkX+9KLAkh450+WRxkx9NO9DvRMi7kfUKhb3E4Wa7Opk35q0w+nFxUx3Iqz5VzU13l7ZY+zPN0GZMFiT4yztFi6I3uBctjcL5Sac6vJpIS1fjpsVbMShZ7eeFiNL+0BZbBWz+cabx4a7Eer7pMuHt3Zz4E7IXuGtoloM9QqpKg5vqgo5JLUDZCj+OKhMGDTnqG1pdte0agYS97oPUkGvEhwZiIS35+smlT4oBNoKsuoEsnhYzss+mJJsidb8sqRIIRRyLpLBDTpDRmFRkyprgWqrHbkOoL4rkZGNoh-GmnszToQuV5ib2jpMaahHujU7yVHuGZHka0E5iZImLtpoFxmu-gJtJr5ERkDT+Lq8G+lmOJ7CaJo2VpIEBGWemVi5bpvJkf6hIpvG+cis6Uu8QXAT2gwpOBA6RexRliEknyOuRiXQWIZp1mldE3kMq5MWkuU7hx-LBmZyllWC9RVd29FoEkd7uHcT4rFurmGTy7yFcVSl8WVFJJJk3VYUysEqv1Bncgt7xqW1s18nFc4aZe6W9UMuGDegsEbX5oTZAeM2lf5e4xUtdl9YxF0gPs13IpSQbcSVk6-ZkMViK9IVDNx9VSSNL5RTd5XeROx44rUDQg+DGV9bpn0LT9HULUj5mitBe4UmhBZAdV2F9Q59XObDbFNWVnlObtj2eWIoSpUdVM9TVhVrRFjMyVBPz+GIkvs0D0ES2CFMdsd1NMlUa05SLY3ckJXPTQlMujjFoTqZTtH8zTNR1Z92yNbJyIEh8X4PfrtafIdJuiRDAkqlS+P+QVHzSyjv0NPsFru7ZnvpN79w22Lksh0T7X+XWVSY6dYLe+isdudB4JSzxPn62IxmNGnNU5t7LEa-DwfGfFhdB2VmSwUkZfm1k3sw1EcN5RSJqtQXyMWRSf4FW3Ks46MWS+1Supjk7jf+bqVLjzGAdro0M+fmagfD-H06r4Mn7e8L3dM7bllbPdeuL9OjRu4rfPLTGBze+rZ+iznlJ5vXQ8k2pYIwSHw9CqA4M8zTTl3v-ZuwYw6P1Ns-QYo5QHDQ-prZMuQTRQP9E9dGPNw7BSxpZUBMdq55U-FSfq2CcT+yAbzBBb1c6gKzmQ5mHwFizmofxEGZpgFlVAVXNBNcaheXRlw3OBwMb0I9kQn4oCu6jWEQcSoixxEUicu8MG0iI6yMnrYH4vtbo-ETntPcDR0Z8PFKAhmQje77H6o7G+w8qhmgfmGBhEMgygNPoo3uMEKRqOep8Vu2jCGnS5qA9+vjmb+SpLdNRAl3hfD4VgtcXNfajj-ADBeziqQ5hSQNUYJpfa5lWoPYmOCnLZGNvAmR4So5pNIbYmJix3he3Ke1B2f43EYR0eE86RSWHNIvuLYujiG4WQ+J+YMKSPpFMEdEkZqYkm6wmSTB2cUtEEJOjVcqKpJa+0yApa+azfw-B5CkvR6ByolOLnsjps1pkAJSXTT6qYMmS08mouWRyUlhTeT4nuMScwpmyU4-+VJeRbNqX0mq2R9lRKBSMvE3wTGPW3imPhRyVTZEMakVJgNF78nRjU9xdS4WFOdKgxZUFPypDxAk8qt0sUNKYs3fGHxHzr0Jbkvc0KyWwvNgSHFQyaU5yyKmCuDz0UNEmj0zSOyhVzOdAspFtK2zbQSbyKUWKoafV+BynMqE0XO0fIVLFVyQAg0NUsUIgSqg5Cxa80YZoOX8hRd8lOwlQmKqVP8l1gLz60u1QVcRn4Q5OT4eaHFiKg3ip1GBaVMt763XwTCsJNUPLxg3Kwi+VICQDx5es4uZp2wCozebEO8ZqVqvFf1DyJrG4zjrlG1ln0Q6GvKpApNTa4KTSjQM2wQkOXJQlGGiWqYy29IrUyBY8ZVVxsMvyFMvJxGFUmqkKNerRgLHximD8Dki3+j3PS0l07fUxnMfGF02cl2LA8nantFll1tIVuWi9DpnVDpsWKpdhUqgnL-se5ulQp0KuVpe-1Q7A2f0Mp5YJO8n0k32JLCkfDjLxljbBuYTkBJVqQ8ej4Bt0OW1GMZfGTkeQEpychvDEp0OUorDWxdOGQYCXGUB6o-Ukl7nQ22sjTTf04dIiHVZnG+p7nrehwdFZRW1rg5+ZRa72PUh9RBwYmiVTbQoyhsRBHqimiEsktTZsmT4i0wo+TOHcjfEAxUgzQYDj8vPeptA7xLX4nxqi4J4j6jNwWOhr9FYf1WeqJNJT+mAh+f7SZxBbmoMVhg+gtADbMiHpo-6T4Jk30udM6WR9TEvj42yG2cRD60OxcYQPJiWX8Ztiy+I6cmiz3gby4MHza5gwcr-BhyLzJ2GLUqxDXU-ZBOhYyFRR9R7UYg2c61uLqBvj9jkyxrjYJevTZ2LKnL82qvKvQN8CjRmpsZa46RXUfC-z9ks6t28hUTvgv9HiSaLWlZtbQEVfsN7c1QTaQ1vr9R6xpvfa5xbQWQBFTq9kB7pzqhZdnJdhLEOkvCMaBEvrRzzVDaIbkArn1XZ7rpWG3Ug3tmg9yKRh8dYKPihh+Js6zc+G5EY+uZj2HqiSzp-ZgIjQQlk-e6gXI-GqdjduzUOsZXahM7iuBSoR2uedLadL-b64F3s4+wr2aeJSfpo-QEeJjl6wAGoKMS4B1kIKAAxRA5OVQ5uGbSnkDRPiNsmbh1TBDrfIAFyztnyWAzinc2G14vIrc24F8Ly6HKYpJI49zmo+xeSvfDF70HMmQArfV0ZKFYn494e+Dty8qeBcq7V-7z8hVJRhqpP7MP3uFvbtsDdrPFfjLpce6CdbwS6+g8td9h34q-z7uryDH4PeBfg5C2Lg4jm7OdKyNt8fC2kco97qaV2rv1ngm5kvxhfZOu+wUqovrM4zSF5T+Hhbj5ZeGIEjFMNRzJ274hlXxyfvUefFfe32H7kK-J9hMXlfpHmMKLlnriOGmGu5oVOfgAZfnvungRLem8O5qRGCj-iIujJ+M-jjirryByhKJUHHknNzBLPKkXnAS-o3vhM3uXjwtzGokbGpHAuWoAXvpavpEgVOJUL8J6jFGBuQfXnvuDk5COshCNn1jyEVJ5NgadF8o5KvmwmpASN-vTpSFSNtDIQLHjqMJ5NHmpJ-gkjkOaJoebFKGtPbkJqCOjDqIErKlIp7hQUQlQmuFKN1ikAbptqTL8PyCYStMAetJwRxHFKuhIXhh8L4TGPsGtJnv7jyNDnPqYvyAJBEZlCrt9IEbLL8CDN8sGHQg4YIRDAtGtDQUoniLhgwc3IzqEqwYUZanjBkZSJKFERITkLdHNgIaDqZC4VPmASCiEZ4RXniDAbYDUU4UjnuCUlUF4ifkkkbO0RfgUUQqrC4VhrEcXKaAkY9DkN8N6vkaDlSN7BYeNrnEVJ9i0cZF1NUY4enCzj7A0VzGlvPB3h6D1sMegKMenMAQJCUs7tkRIYnsZCkWKJnCUrdPCqEUGBoVcYsenCrmCBkl5EQXtOoRVnsRHlQRniUX4sErUFqryGQQsfsZatPA0U5hnBIaODyLsemh8eXODpvKSaONyqdr9OKJitCfsUjh8BkilEiY9Eco+PwYSQLq-BvKsUouLFmhIcoYsECbLKAkcdPn7F8GopLEctSSwdcTVMgmuDyL7CmMEpvjgvHKnBySKcAaON1qhHItKf1FgWaQtgErqTER-kbPyKqZSRqdOrSebP5AIt1kVJphIQVJgnKTaUxP5IYqhM0Z4f5PUEGGGZagYg0RLBLGgaoTBOVGGeDmpFvPimov5D8P-iMVqb6UjuKCUqzEaX5IsJ-nKejhGeKb3OaPWJro9EwVUWiQtqkkxOkvce5v0SybnEcvRg6YwqGmku-s2SnE8egQbCaHzjSaWUyMfr2aAbEaDCmMTsZLBPWenosL7EJJKNWRkFliHASbATCbsirqRIeWpDGUOdMo+DrpqVeebPcr2ViTEuYjFLnsQbOAfGORDKmPsv3pYciCHFUH+XtJKL8G8SAD6SueDu8g0QKQ+c8aTMEv1PWUjsXAiZCgWaPsDt6cuTGOCb2U2cCvfCedBNOHFMWe8aRYMNimuLiimbOMXKqbdKhHKc3DilOTErdFSL-PHj8HWB5LxcAeyhkdvHfKqc7qXEBUQsKqxS6eQl6B4UOUvOjIua+aDjwaxWXqjiDEkpsUXC7ljl2Ywn8Wyl+XmoGMfrGdkLPLxX3mBccTmLiCJUnAVG0kKZefpeDq6jJWpK2AkkVNhUpadPfqxQoXmo0JSDRaOBxS+SRW+bOtoc6JRfFdtEGbGdzMXMwWlb3pTugOaByhSHfpAVlo6lFZmizh5BVa7O6SfujC7qlZpIhZesAR2jJSDAsLOfTlkEwV6Z1UxSlunsOjJV5F0QMQAmPnVZWirqhByvishNXqkKOVZRDHpkxLuhkZXnWGZU2ryJ5PBV1Q6JaujHuviCSuOvirpcVQLrKvGD0f7oTM3N5bNIVN0heSWelZBvGHFVBLBMsg0p4XytkMRWNQDRpplWVdlSDbjldn1iekGKNR0RPqVSAORgdZKEJHyTLPyJomPItWZizhKHurdC7oTY3PyIsMXHKW0lpuucIp5M3GzKjc7uVAxQheNbGOnm0hRi9nkKjV8GCUzSrtphkZ6EyWuvUPsLzRdW5hiZohRqRPWOmfHpzHSkzR5u5WLvUJBW2TLHiK8B1ZjQtkklpm9WzaHLNUORLPuH9YxbDfFlpsDTnFyhzb5lMVCdtUQv9oVojV7XWMGLTRZLkDHvMQFQLtVvjoqVnjxmbp4Z-osBjcKcvizl1hkeedGn1viMhNDZbVVsAcEnVlkibY3MbedfzUtp1mpTEu5v9p4cXEJEVTDaDi7v2EZepbFGov+C7XzW7YthiS7qtbBFXZMm3f5f9V3Zan+Huv+lPchv+LXSPQYZ1rbXlOvuCZ4WdR7kuRvUjp-jpmCCvU9jyPWHKbjv2CHYZEkqKanTFEPcrYLjkLLonf7pjhfdUNON3mTb2KLXpDkHukypAbKjfZULLqzTvUGL-RJgjoA6BDLobo3RfEVAg4LvTVA7gXFMVinUOWlrPa7eTgbiA2ICbhkWllg83K3AALotAgDEBQByBQBqBGCgBxAACecoxgIAyAVgAA1mgKAJgNwzgKMFYOsM4AAO40DKD0BoBcyPrwA0BkBYB9RKAAAeAA8gAGb6MQBwCYB9QSQgDcMGNGMmP65KCsOCBsCwgADEAAogAEKCkuAgBNCQiCMiOaAgDiOSO2DSOlByMKNKMBhKBqMaOmPv06NWPGNxP8DmOWOGNJMBAsj2OOO2CuMeOPheM+OWhlCYCRgBOYBwDaNxMgBuNsBsAIDWAeBMAMAQCmNKBICyCwA5PoCtNIBWBtMqDcNuYsj6NyDVMADK5AbAngAAql4M4KM7IJgOMzQAAF4hBbkgAQDMAlM9ARBIDKDKA0CyBkC2NbM7N0BlMgAzMADSCgHglgCAbAZAVgSAOAMANAUABgSg2zTAuzcAluYzKz6zoUPzFzpTALYzAA6nAOo5o+gEwGwIIHSEw347YBU1U945aGi+UxI1IzI0oPI4ozAO9NE7C7EwEAk+kzY6gPwGYRY4kzS5KI+tk7CEwHEFACIz44w5aDE-C+jv86I4E5U9Uw7kgP0K01YAwKUAwNI-cwAOR1g5odNdOwi9P9PODKDaNoApOEjKBDNDCOiLPLNrMhDSFKA4vCuYuQisOdMcOoD8NEuRPuFktwtxPJxKCYCvOyAQCjNWAICcMgD6M0CCAVOdCgDBtwDIu2BkpKBwAACODAOgok3LSgPDfDoAOLYjeLtgTAfTzgrLuTVIAAwqED4OEEw+YKw0cyc0K9qwE5G9G+gAPu6J6zm+gImx0yU-EKQM4DIBq+gJYNAO0Mc6c0wwaxGzQFG8oLYPeG28E+gI4zW8mz8443E5O9O7OzeEoEu+GEO1ACO7W0w9APCAEzgAczW2QF4LILIHKKEJQPku09ozQAYAE441O0syE2694z47430-49mwuyAMILe84Mc2GzgEi2oKMK03ADgPwEwHAH6xcJK2wEI3AFCxEySzUHY0i90yAE43WJkMWy4PcJW502wJe3W0K42zO82yyfO6MJ20s3QD2yh2u7YPu4e2O0oBO0G1O0206Ix7YEu8cyu1sxxw2wJ3R1jDu1YJeFxxYKO1iyAEgM+6+7ILEIIL+9i-+0K0E-i2E4S1h8M66xS0MFk3h84yW2WxW3GxR1RwE-W1oDoHoLeBaBY0K9oLoBs7KUU6AKoOoF565-oJw00DywI3p7i0BxiwM7F3cFqB4IsYW+gLIx8xUws0C6a6C0G9C+S-CyAIi8i6cOR9W8p058Fz5+5+O5V25xZ8JP55F8I-p+2yAKEwM069h93RgPl+65Zw47CGlyICp1W5R+V6AM58wyF2gABLx7VyEJLDpwF2oBoC5z56+8YOF6i1F4B6MPF56yK0YF9GSElwqDgE7CAPQ7hwN7k0RyR6Qsa8C2a2WMazC9+wi0iyi-Z2V7WxVwE953V7N55-99N2VL+1d21-oEi72wEye2U6AAayAMc5YJIycJ+0tyAJ131Gbny314+oK+gM4F6x07644wGw65O6G3KBu4J7GyAAm0m4IHPZGKm8B0gLw50Pw1m4E613mzYNd-h04+YsWyL+yKV2N79xNzR9J7YC2w1Dz0B8x922UL2zV1J5u+gHOwr6MKJ7IOJ-2+u-xxr7JyALu7CIp1R8e+w-DyAOe4c6O9e7e50Pe4+6p+p0K3EIh4IK+-ozoMY7+3+819F6MCBxcOB9YJB08DBxU-B4h8h32162hxhyZzhyAClwR2HUGIU99xL6c39zTzJ5tsJx20myx+oCr04GrwX1uxcAZyJ-J2J0z6uwO9X5r9u6b-J3u-oAe0p0e0+y+2gJp4INp419z3X+gO1+E8S-rqo716S2n1Z7k8L6LyNw5+NyAJNwDyEICXNyD1V-Vxj4F6t1N+t2FxF2P61-t1a9U0RB4Po44en0Nxl0oI99l4Li93l+94V59yVzn451L3vzq479gea3OrimAa6B8AO2vEJgS0x4p9uuuPJKAL0G7pdK+f-dfpv1B68gPOfHLfsozBiNcj+83DbsAC24Wsdu0A9AFf3i4OtjuVQO-o4XO56xLuyA27shCz6ZclmT3HLq9zn4fdiuNgcXv-w37zcAgBwKvifzq7+RweSgaRjIEEAw9QAcPEIAj1sDI84OsodHty0hAE9QAKrGAPh3VYDN9WbmfHod1oHjM2AsrA9qgA8BWNPmngP1h4AAByGoHQB4HGbl8X2ZQL5s4A8BOMqgPgdnsWxgB9NMAIQnQD0BOZwBXgpCEwK83eafNbBAAAQgChDlA+jKwOowYA0AWBuXT9ugEmZkBpmHgOZpwJNYgtBcDSXgV-2ECxNTgabY5nAAAASfAlINtyD7X9vGEPW1sGzz6gA7ewgzANEDOY9B9GcTLKG13e65AmGxAKdrIyFaod0Og-LTkw2Na2AihJQuZh4AAAy37fvq+wC71MkAxzYtov3QBOMOKNNZwJ7yjaAsChIATYbM3mZpskAXve4RULNYOQCeQ-QQK8K95nCbuFw2oCCPRBMM1OL7AABoABFUvsrxoCKCO+H7apsMJwCatjhxzNAL7295wAlALzBRoCO6agBKm53WwAAApAuDABAJQC34eAAApB4FxxKsAAlB4AAC8bIjwKEA8AAB+DwPKycY+AxAPgHwC41CDysPAtg+VvKxU4+ChGPvP3riMCafMhGZwhgAUMJC3DBA+ze3r9xZBajLcugNIViMVH-Co2LjbRqSMHZqAqRNIkLuyM5Hci+RlI6kbSMlEeAvW6o9hhUwpE2jXRIXe5ukA8AeAFA8rLIbE3lYKt5WzIlThCIgAABNHwC+ygDSMMu5TFUdwOgiesVRhI8NvT0tGwhfRmAW0bSIZG5BWRHIrkbyP5GXCaas4CUVKJlFMMtROo4QSSPN5+i7RPnB0YyLrDVikg7ol0V2L0A9inRjIgcbYITDNi3hUbRlsk2WAGisulQ4kQWM46djaRlY+VpgiNwSi+RYgd0XiBU5ajcxQrdseSKHGljexFYx0dWIFGgjagDY-kU2KUCrN1B9bEMAvztaG8IA57KAOV34AECmgQAA).

<p align="center">
  <img src="https://github.com/shadfrigui/vega-lite/blob/fff31ae7ba56d1e390912627a50b6e034e73fb20/uk-population-2020/images/uk-population-2020-original.png" />   <img src="https://github.com/shadfrigui/vega-lite/blob/fff31ae7ba56d1e390912627a50b6e034e73fb20/uk-population-2020/images/uk-population-2020-recreated.png" width="600" 
     height="817" />
</p>
<br />
