---
layout: post
title:  "il Manifesto 2 pdf"
date:   06-10-2018
categories: tools
---
<br />

<script type="text/javascript" src="../js/jquery-3.3.1.min.js"></script>
<script type="text/javascript" src="../js/manifesto.js"></script>

<style> 
input[type=text] {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    box-sizing: border-box;
    border: 2px solid red;
    border-radius: 4px;
    background-color: #093750;
}
</style>

<center>
	Inserisci l'url all'articolo de Il Manifesto che vuoi scaricare: <br>
	(Es.: https://ilmanifesto.it/politiche-incostituzionali-class-action-contro-la-casa-bianca/)<br><br>
<form id="frm1">
  <input type="text" name="fname" value="URL COMPLETO"><br>
</form>
<br>
<button onclick="myFunction()">Ottieni PDF</button>
</center>

<p id="link"></p>

<script>
function myFunction() {
    var x = document.getElementById("frm1");
    var text = "";
    var i;
    for (i = 0; i < x.length ;i++) {
        text += x.elements[i].value;
    }
    link2pdf(text);
}
</script>

  
[Massimo](https://twitter.com/massimobedini)
