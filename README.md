def suma_cyfr(liczba):
    """
Suma cyfr 
    :param liczba: liczba jako tekst z ktorej obliczamy sume 
    :return: wartosc calkowita ktora jest suma cyfr
    """
    suma = 0
    for cyfra in liczba:
        suma = suma+int(cyfra)
    return suma


def pierwiastek(x):
    i=1
    while i*i<x:
        i=i+1
    return i

def czy_pierwsza(liczba):
    for i in range(2,pierwiastek(liczba)):
        if liczba % i == 0:
            return False
    return True

with open("liczby.txt") as dane:
    ile_liczb = 0
    for wiersz in dane:
        liczba = int(wiersz)
        if liczba %2 ==1:
            #print(liczba)
            ile_liczb +=1
        if suma_cyfr(str(liczba)) == 11:
            print("suma",liczba)
        if liczba>4000 and liczba <5000 and czy_pierwsza(liczba):
            print("pierwsza",liczba)

    print("Liczb nieparzystych", ile_liczb)


print(suma_cyfr.__doc__)





liczba_kobiet = 0
liczba_mez =0
listopad =0
with open("dane.txt") as dane:
    for wiersz in dane:
        pesel = wiersz.strip();
        miesiac = int(pesel[2:4])
        if int(pesel[-2])%2==0:
            liczba_kobiet=liczba_kobiet+1
        if pesel[-2] in["1","3","5","7","9"]:
            liczba_mez=liczba_mez+1
        if miesiac == 11 or miesiac == 31:
            listopad+=1
        liczba_kontrol = 0
        mnozniki = [1,3,7,9,1,3,7,9,1,3,1]
        for i in range(len(pesel)):
            liczba_kontrol+=mnozniki[i]*int(pesel[i])
        if liczba_kontrol%10!=0:
            print(pesel)
        #print(pesel,pesel[-2])
print("liczba mezczyzn",liczba_mez)
print("liczba kobiet",liczba_kobiet)
print("liczba osob z listopada",miesiac)





def czy_liczba_pierwsza(liczba):
    for i in range(2,liczba):
        #TODO: optymalizacja
        if liczba % i == 0:
            return False
    return True

def suma_cyfr(liczba):
    """"
    funkcja obliczajaca sume cyfr z liczby
    :param liczba: liczba z której obliczamy sume cyft zapisana jako tekst
    :return: suma cyfr
    """
    suma = 0
    for cyfra in liczba:
        suma = suma + int(cyfra)
    return suma


ile_nieparzystych = 0
with open("liczby.txt") as dane:
    for wiersz in dane:
        liczba_tekstowo = wiersz.strip();
        if suma_cyfr(liczba_tekstowo) == 11:
            print(liczba_tekstowo)
        liczba = int(wiersz)
        if liczba >4000 and liczba<5000 and czy_liczba_pierwsza(liczba):
            print("Liczba pierwsza",liczba)
        if liczba % 2 == 1:
            #print(liczba)
            ile_nieparzystych = ile_nieparzystych +1

print("liczb nieparzystych jest",ile_nieparzystych)
#with powoduje że plik zamknie sie po wyjsciu z instrukcji
#kazdy otwarty plik musi byc zamkniety !!!!
print(suma_cyfr.__doc__)






#algorytmy tekstowe
#palindrom
#wczytaj słowo i sprawdź czy jest palindromem

def czyPalindrom(slowo):
    if slowo == slowo[::-1]:
        return True
    return False

print("podaj słowo")
slowo=input()
if czyPalindrom(slowo):
    print(slowo, "jest palindromem")
else:
    print(slowo,"nie jest palindromem")

# anagramy
#sprawdź czy dwa słowa są anagramami czyli składają się z takich samych liter w tej samej liczbie

def czyAnagramy(slowo1,slowo2):
    lista1=list(slowo1)
    lista2 = list(slowo2)
    lista1.sort()
    lista2.sort()
    if lista1 == lista2:
        return True
    return False

slowo1=input()
slowo2=input()
if czyAnagramy(slowo1,slowo2):
    print("tak")
else:
    print("nie")

#wczytaj slowo i powiedz jaka litera występuje najwięcej razy i ile
slowo = "ejjżyraafaryżje"

zbiorLiter = set(slowo)
maks = 0
teLitery =[]
for litera in zbiorLiter:
    if maks<slowo.count(litera):
        maks = slowo.count(litera)
        taLitera = litera
        teLitery = [litera]
    elif maks == slowo.count(litera):
        teLitery.append(litera)

print(teLitery,maks)

#wczytaj liczbę i sprawdź czy jest liczbą pierwszą
print("podaj liczbę")
liczba=int(input())
def czyPierwsza (liczba):
    for i in range(2,int(liczba**0.5+1)+1):
        if liczba % i == 0:
            return False
    return True

if czyPierwsza(liczba):
    print(liczba,"jest pierwsza")

#wypisz wszystkie liczby pierwsze mniejsze od liczby wczytanej
pierwsze1 =[1 for i in range(liczba+1)]
pierwsze2 = []
for i in range(liczba+1):
    pierwsze2.append(1)
pierwsze1[0]=0
pierwsze1[1]=0
for i in range(2,liczba+1): #zlozoność na pierwiastek
    if pierwsze1[i] == 1:
        for k in range(2*i,liczba+1,i):
            pierwsze1[k]=0


for i in range(liczba+1):
    if pierwsze1[i] == 1:
        print(i)

print("podaj dwie liczby")

a=int(input())
b=int(input())
while b!=0:
    a,b=b,a%b
print(a)






zmienna = 12
print("podaj liczbę")
liczba=int(input())
print(liczba)
if liczba%2 == 0:
    print(liczba,"jest parzysta")
else:
    print(liczba," jest nieparzysta ")

#wypisz liczby dwucyfrowe parzyste
for i in range(10,100,2):
    print(i,end=", ")

slowo="informatyka"
print(slowo)
for litera in slowo:
    print(litera, ord(litera) )

while liczba!=0:
    print("podaj 0")
    liczba=int(input())

import random
losowe = [];
for i in range(10):
    wylosowana = random.randint(1,10);
    losowe.append(wylosowana)
print(losowe)
losowe.sort()
print(losowe)
print(sum(losowe))
print(min(losowe))
print(max(losowe))

zbior = set(losowe)
#wypisz ile razy wylosowały się poszczególne liczby
for element in zbior:
    print(element,losowe.count(element))






    def wczytajTablice():
    listaWczytanych = []
    print("podaj 10 liczb")
    for i in range(10):
        print("podaj element", i)
        listaWczytanych.append(int(input()))
    return listaWczytanych


def szukajMaks(lista, indeks):
    maksymalna = lista[indeks]
    zwroconyIndeks = indeks
    for i in range(indeks + 1, len(lista)):
        if maksymalna < lista[i]:
            maksymalna = lista[i]
            zwroconyIndeks = i
    return zwroconyIndeks


def sortuj(lista):
    """
    funkcja sortuje tablicę przez wybieranie
    :argument lista: tablica do posortowania
    :return: posortowaną tablicę
    """
    for i in range(len(lista) - 1):
        indeks = szukajMaks(lista, i)
        lista[i], lista[indeks] = lista[indeks], lista[i]

    return lista


tablica = wczytajTablice()
print(tablica)
print(szukajMaks(tablica, 3))
print("posortowane malejąco")
print(sortuj(tablica))
#print(print.__doc__)
print(sortuj.__doc__)





https://cke.gov.pl/images/_EGZAMIN_MATURALNY_OD_2015/Arkusze_egzaminacyjne/2018/formula_do_2014/informatyka/MIN-R2_1P-182.pdf
with open("slowa.txt") as dane:
    ile_na_a = 0
    ile_zawiera = 0
    ile_anagramow =0
    for wiersz in dane:
        slowa = wiersz.split() #split wstawia tekst do listy domyslnie rozdzielony spacja
        #print(slowa)
        #print("pierwsze ",slowa[0])
        #print("drugie ",slowa[1])
        if slowa[0][-1] == "A":
            ile_na_a+=1
            print(slowa[0])
        if slowa[1][-1] == "A":
            ile_na_a+=1
        if slowa[0] in slowa[1]:
            print("zawiera ",slowa)
            ile_zawiera+=1
        litery1 = list(slowa[0])
        litery2 = list(slowa[1])
        litery1.sort()
        litery2.sort()
        if litery1 == litery2:
            print("anagramy ",slowa)
            ile_anagramow+=1
print("słów kończących się na A jest ",ile_na_a)
print("liczba wierszy w ktorych pierwsze slowo zawiera sie w drugim",ile_zawiera)
print("liczba anagramow",ile_anagramow)
