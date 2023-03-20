<h1>HTML: Hyper Text Markup Language</h1>

<a target="_blank" href="https://github.com/rohitjethoe/codekamp">
    <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/rohitjethoe/codekamp?style=social">
</a>

<br />

HTML is de markup taal die in de browser wordt gebruikt om webpagina's te creeëren. Het legt de basis voor iedere Web Developer en het is dus absoluut benodigd om de syntax te kennen als je dat je doel is.

## Een simpel HTML bestand

```
    <!DOCTYPE html>
    <html>
        <head>
            <title>Homepagina | Henk Krols website</title>
        </head>
        <body>
            <h1>Mijn eerste heading</h1>
            <p>Mijn eerste paragraaf</p>
        </body>
    </html>
```

<div class="window">
    <div class="windowBar">
        <div class="circle circle-1"></div>
        <div class="circle circle-2"></div>
    </div> 
    <div class="result">
        <h1>Mijn eerste titels</h1>
        <p>Mijn eerste paragraaf</p>
    </div>
</div>

Voorbeeld uitgelegd:
- ```<!DOCTYPE html>``` vertelt de browser dat de versie HTML5 wordt gebruikt.
- ```<html>``` de kern van een pagina, alle html code die geschreven wordt komt hierin.
- ```<head>``` hierin staat alle meta data van een pagina, zoals de titel.
- ```<body>``` hierin staat
- ```<title>``` geeft de titel van de pagina.
- ```<h1>``` wordt gebruikt voor titels
- ```<p>``` wordt gebruikt voor paragrafen


<iframe width="560" height="315" src="https://www.youtube.com/embed/c3Dvxl6LBKA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<style>
    .result {
        font-family: none;
        padding: 0;
        margin: 0;
    }

    h1 {
        font-weight: 500;
        margin: 10px 0px;
    }

    p {
        margin: 10px 0px;
    }

    h2 {
        font-weight: 400;
        background-color: #dfe2cf;
        display: inline-block;
        padding: 2px 8px;
        margin: 10px 0px;
    }

    pre {
        padding: 20px 10px;
        margin: 10px 0px;
        border-radius: 4px;
        margin: 10px 0px;
    }

    .windowBar {
        background-color: #ddd;
        padding: 10px 10px;
    }

    .circle {
        width: 16px;
        height: 16px;
        margin: 0px 4px;
        border-radius: 100%;
        display: inline-block;
    }

    .circle-1 {
        background-color: #FF605C;
    }

    .circle-2 {
        background-color: #FFBD44;
    }

    .result {
        padding: 10px 20px;
    }

    .window {
        background-color: #fff;
        box-shadow: rgba(149, 157, 165, 0.2) 0px 4px 12px;
        margin: 20px 0px;
    }

    li {
        margin-left: 20px;
    }

    iframe {
        margin: 20px 0px;
        width: 100%;
    }
</style>
