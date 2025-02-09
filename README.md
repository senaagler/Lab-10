# Lab-10
Tc
//230202042 Sena Güler

#include <stdio.h>
#include <stdlib.h>
#include <math.h>

void TCKimlik(char *dizi)
{
    int i;
    int cift=0;
    int tek=0;

    if (strlen(dizi)!= 11)
        {
        return 0;
    }

    for (i = 0; i < 11; i++)
        {
        if (dizi[i] < '0' || dizi[i] > '9')
            {
            return 0;
        }
    }

    if (dizi[0] == '0')
        {
        return 0;
    }


     cift = (dizi[0] - '0') + (dizi[2] - '0') + (dizi[4] - '0') + (dizi[6] - '0') + (dizi[8] - '0');
     tek = (dizi[1] - '0') + (dizi[3] - '0') + (dizi[5] - '0') + (dizi[7] - '0');


    if (((tek * 7 - cift) % 10) != (dizi[9] - '0'))
        {
        return 0;
    }

    int toplam = 0;
    for ( i = 0; i < 10; i++) {
        toplam += dizi[i] - '0';
    }

    if ((toplam % 10) != (dizi[10] - '0')) {
     return 0;

    }

    return 1;
}




int main()
{
    int sayi[12];
    printf("11 haneli bir TC kimlik numarasi girin: ");
    scanf("%d",sayi);

    if (TCKimlik(sayi))
        {
        printf("girilen  TC kimlik numarasi  uygundur.\n");
    }
     else
    {
        printf("girilen  TC kimlik numarasi uygun degildir.\n");
    }

    return 0;
}





