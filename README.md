# nCrypter-GUI
simple text encryption program with Qt GUI 

---
![demo](demo.gif)

N-Crypter is simple standalone Text encryption/decryption tool
wriiten in GCC C++


> note :this is a simple encrypter anyone with source code could simply decrypt it !

this is a fun project , sorry for bugs


### Prerequsties
---
> g++ &
> Qt v.5

### How this works

this program simply change every text to its ASCII value and change that ASCII value and reconverting to Text

```cpp
QString ncrypter::encrypt(QString text){
    for(int i=0 ; i<text.size() ; ++i){
        int key = i%4;
        QChar tempchar = QChar(text[i]);
        int num = tempchar.toLatin1();
        switch(key){
            case 0 : num ++;
            break;
            case 1 : num += 2;
            break;
            case 2 : num += 3;
            break;
            case 3 : num += 4;
            break;
        }
    char newchar = num;
    text[i] = newchar;
    }
    return text;
}

```

the decryption is also work in almost same way the only change is while encryption
convert the charecter to next ones decrytion converts it to previous one

