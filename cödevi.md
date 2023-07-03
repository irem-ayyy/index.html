ödev 1:
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];

    printf("Bir kelime veya cumle girin: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0'; // Newline karakterini kaldırma

    int length = strlen(str);
    printf("Girilen kelimenin uzunlugu: %d\n", length);

    return 0;
}

ödev 2;
#include <stdio.h>

int factorial(int n);

int main() {
    int num;

    printf("Bir sayi girin: ");
    scanf("%d", &num);

    int result = factorial(num);

    printf("%d! = %d\n", num, result);

    return 0;
}

int factorial(int n) {
    if (n == 0 || n == 1) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
}

ödev 3;
#include <stdio.h>

int main() {
    int num1, num2;
    int* ptr1;
    int* ptr2;

    // Değer atama
    num1 = 10;
    num2 = 20;

    // İşaretçi atama
    ptr1 = &num1;
    ptr2 = &num2;

    // Değerleri ekrana yazdırma
    printf("num1: %d\n", *ptr1);
    printf("num2: %d\n", *ptr2);

    return 0;
}

ödev 4;

#include <stdio.h>

int main() {
    double number;

    printf("Bir ondalik sayi girin: ");
    scanf("%lf", &number);

    printf("Sayinin onaltilik (hexadecimal) karsiligi: %a\n", number);

    return 0;
}

ödev 5;

#include <stdio.h>

int main() {
    FILE *dosya;
    char metin[] = "Bu bir metin dosyasidir.";

    // Dosyayı oluşturma ve yazma modunda açma
    dosya = fopen("metin.txt", "w");
    
    // Dosyaya metni yazma
    fprintf(dosya, "%s", metin);
    
    // Dosyayı kapatma
    fclose(dosya);

    // Dosyayı okuma modunda açma
    dosya = fopen("metin.txt", "r");
    
    // Dosyadan metni okuma ve ekrana yazdırma
    char karakter;
    while ((karakter = fgetc(dosya)) != EOF) {
        printf("%c", karakter);
    }
    
    // Dosyayı kapatma
    fclose(dosya);

    return 0;
}
