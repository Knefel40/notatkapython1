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


