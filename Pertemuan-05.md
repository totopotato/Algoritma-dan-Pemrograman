# Tipe Data, Variabel, Konstanta dan Operator

Pada dasarnya hanya tipe data angka ` BOOLEAN ('0' dan '1') ` yang dapat di proses atau dikenali oleh komputer. Namun demikian dalam Bahasa C telah dikembangakan beberapa jenis tipe data lain yang dapat di proses dalam program. Tipe data tersebut di bagi dalam tiga kelompok sebagai berikut:

No | Tipe data dan Keterangan 
--- | ---
1 | ***Dasar*** berupa data aritmatik yang terdiri atas (a) angka Integer (bilangan bulat) dan (b) angka pecahan (folating-point)
2 | ***Enumerated*** serupa dengan aritmatik (integer) digunakan untuk mendefinisikan variabel yang hanya dapat diisi dengan nilai bilangan bulat tertentu.
3 | ***Void*** kata (penentu) void digunakan untuk variabell atau fungsi yang tidak memiliki nilai apapun (kosong).
4 | ***Turunan*** termasuk di dalamnya adalah Pointer, Array, Sturcture, Union, dan Function.

Tipe data Array dan Structure termasuk dalam kelompok kolektif, tipe data untuk Function adalah tipe data yang akan dihasilkan dari sebuah function (fungsi). Berikut adalah contoh detail dari tipe data dasar.

## Integer

Tabel berikut ini berisi daftar tipe data integer yang dikenal dalam bahasa C

Tipe | Ukuran dalam memori | Range nilai 
--- | --- | ---
char | 1 byte | -128 to 127 or 0 to 255
unsigned char | 1 byte | 0 to 255
signed char | 1 byte | -128 to 127
int | 2 or 4 bytes | -32,768 to 32,767 or -2,147,483,648 to 2,147,483,647
unsigned int | 2 or 4 bytes | 0 to 65,535 or 0 to 4,294,967,295
short | 2 bytes | -32,768 to 32,767
unsigned short | 2 bytes | 0 to 65,535
long | 4 bytes | -2,147,483,648 to 2,147,483,647
unsigned long | 4 bytes | 0 to 4,294,967,295

Untuk mendapatkan ukuran variabel yang sebenarnya (dalam platform tertentu) dapat menggunakan operator ` sizeof `. Ekspresi ` sizeof(obyek) ` menghasilkan ukuran memori dari ` obyek ` dalam satuan ` byte `. Berikut ini adalah contoh kode untuk mendapatkan ukuran memeori sebuah variabel:

	#include <stdio.h>
	#include <limits.h>
	
	int main()
	{
		printf("int memerlukan memori : %d byte\n", sizeof(int));
		
		return 0;
	}

## Floating-Point (angka Pecahan)

Tabel berikut ini berisi tipe data angka pecahan yang terdapat dalam bahasa C:

Tipe | Ukuran memori | range nilai | Kepresisian 
--- | --- | --- | ---
float | 4 byte | 1.2E-38 s/d 3.4E+38 | 6 decimal places
double | 8 byte | 2.3E-308 s/d 1.7E+308 | 15 decimal places
long double | 10 byte | 3.4E-4932 s/d 1.1E+4932 | 19 decimal places

header ` float.h ` dapat dicantumkan dalam program untuk menggunakan tipe data float dalam program, seperti contoh berikut:

	#include <stdio.h>
	#include <float.h>
	
	int main()
	{
		printf("Ukuran memori untuk variabel float : %d byte\n", sizeof(float));
		printf("Minimum float positive value: %E\n", FLT_MIN );
		printf("Maximum float positive value: %E\n", FLT_MAX );
		printf("Precision value: %d\n", FLT_DIG );
		   
		return 0;
	}

Hasil dari contoh program di atas adalah sebagai berikut:

	Storage size for float : 4
	Minimum float positive value: 1.175494E-38
	Maximum float positive value: 3.402823E+38
	Precision value: 6


## void

void digunakan untuk menunjukkan bahwa sebuah variabel atau fungsi tidak memiliki nilai, digunakan dalam tiga keadaan:

No | Keterangan 
--- | ---
1 | ***return sebuah fungsi berupa void*** sebuah fungsi mengembalikan / menghasilkan tipe data void. Terdapat beberapa fungsi dalam bahasa C yang tidak mengembalikan nilai atau dapat dikatakan menghasilkan data void. Contoh: ` void exit(int status); `
2 | ***Argumen sebuah fungsi berupa void*** Argumen dari sebuah fungsi dapat berupa void, Terdapat beberapa fungsi yang tidak  memerlukan argumen atau memiliki argumen berupa void, contoh: ` int rand(void); `
3 | ***Pointer yang menunjuk kepada void*** pointer yang menunjuk kepada tipe data void, menerangakn sebuah alamat memori tetapi tidak mengandung tipe data apapun. Sebagai contoh fungsi untuk memesan memori ` void * malloc ( size_t_size ); ` fungsi tersebut mengembalikan  sebuah pointer yang menunjuk ke void, yang kemudian dapat ***di-CAST*** (diubah) menjadi tipe data apapun.

# Variabel

Variabel adalah sebuah nama yang diberikan kepada area penyimpan data (memori) yang isinya dapat dimanipulasi oleh program. Setiap variabel dalam bahasa C memiliki tipe tertentu, yang akan menentukan ukuran memori yang akan digunakan (dalam satuan byte), range nilai yang dapat disimpan, dan operasi yang dapat dilakukan pada variabel tersebut. 

Nama variabel dapat disusun dari HURUF, ANGKA, dan UNDER_SCORE (garis bawah). Dapat berawal dari HURUF atau UNDER_SCORE. Huruf besar dan huruf kecil dibedakan (case-sensitive).  Berdasarkan pada tipe data yang telah dijelaskan pada bagian sebelumnya maka tipe variabel dalam bahasa C antara lain adalah sebagai berikut: 

tipe | Keterangan 
--- | ---
**char** | ukuran 1 byte, untuk menyimpan satu huruf atau sebagai angka bulat
**int** | angka integer yang paling banyak digunakan dalam bahasa C
**float** | A single-precision floating point value
**double** | A double-precision floating point value
**void** | tanpa tipe

Selain itu variabel dalam bahasa C juga dapat berupa tipe data turunan seperti **Enumerate**, **Pointer**, **Array**, **Structure**, **Union** dll. yang akan dijelaskan lebih detail pada bagaian selanjutnya.

## Definisi Variabel dalam C

Mendefinisikan variabel berarti mengatakan kepada kompiler dimana dan seberapa besar memori untuk variabel, dalam definisi terkandung tipe data dan satu atau lebih nama variabel seperti contoh berikut: 

	tipe  nama-nama_variabel;

dimana ` tipe ` harus berupa tipe data dalam bahasa C yang valid seperti **char**, **int**, **float**, **double**, **bool** atau seberang obyek yang di definisikan oleh programmer.  Sedangakan ` nama-nama_variabel ` dapat terdiri atas satu ata lebih nama identifier yang dipisahkan dengan tanda **KOMA**. Seperti pada contoh berikut: 

	int    i, j, k;
	char   c, ch;
	float  f, gaji;
	double d;

Variabel dapat diinisialisasi (diisi dengan sebuah nilai awal) pada saat di deklarasikan. Inisialisasi berupa ekspresi yang terdiri atas tanda sama-dengan diikuti dengan sebuah konstanta.

	tipe nama_variabel = nilai;

beberapa contoh antara lain sbb:

	extern int d = 3, f = 5;    // declaration of d and f. 
	int d = 3, f = 5;           // definition and initializing d and f. 
	byte z = 22;                // definition and initializes z. 
	char x = 'x';               // the variable x has the value 'x'.

Untuk definisi variabel yang tidak diikuti dengan inisialisasi, jika tipe datanya meenggunakan memori statik akan diinisialisasi dengan **NULL** (Semua byte bernilai nol), jen is variabel yang lainnya tidak didefinisikan nilai awalnya.

## Deklarasi variabel dalam C

Dekalrasi variabel sangat berguna bila dalam program terdapat beberapa file sumber. Definisi variabel dalam sebuah file sumber dapat digunakan juga oleh file sumber yang lain dengan menyertakan keyword  ` extern ` pada saat mendefinisikan variabel.

Variabel dapat didefinisikan beberapa kali dalam sebuah program, tetapi dalam satu file sumber sebuah variabel hanya boleh dideklarasikan sekali saja. 

Contoh:

	#include <stdio.h>
	// Variable declaration:
	extern int a, b;extern int c;
	extern float f;
	
	int main ()
	{
		/* variable definition: */
		int a, b;
		int c;
		float f;
		 
		/* actual initialization */
		a = 10;
		b = 20;
		c = a + b;
		printf("value of c : %d \n", c);
		f = 70.0/3.0;
		printf("value of f : %f \n", f);
		
		return 0;
	}

## Konstanta dan Literal 

Konstanta adalah sesuatu yang bernilai tetap dan program tidak dapat merubah nilainya selama program dieksekusi. Nilai tetap ini juga disebut **literal**. 

Konstanta dapat berupa sebarang tipe data seperti konstanta integer, konstanta floating-point, konstanta character, dan literal string. Selain itu juga terdapat konstanta berupa enumerate.

sebuah konstanta (constant) di kelola seperti halnya variabel biasa kecuali nilainya tidak dapat di modifikasi setelah didefinisikan. 

### integer literal 

Integer literal dapat berupa angka biner (basis 2), desimal ( basis 10), octal (basis 8), atau hexadesimal (basis 16). Untuk menentukan jenis angka yang digunakan tanda awalan,  ` 0x ` atau ` 0X ` untuk angka heksadesimal, dan ` 0 ` untuk angka octal.

integer literal juga dapat memiliki tanda akhiran, kombinasi dari ` U ` (untuk jenis unsigned long) dan ` L ` (untuk jenis long).  Berikut ini adalah beberapa contoh literal integer: 

	212         /* Legal */
	215u        /* Legal */
	0xFeeL      /* Legal */
	078         /* Illegal: 8 is not an octal digit */
	032UU       /* Illegal: cannot repeat a suffix */
	
	85         /* decimal */
	0213       /* octal */
	0x4b       /* hexadecimal */
	30         /* int */
	30u        /* unsigned int */
	30l        /* long */
	30ul       /* unsigned long */

## Floating-Point literal

Literal untuk angka pecahan terdiri atas, bagian integer, dan bagian desimal (dibelakang tanda titik/koma) atau bagian angka pecahan, dan bagian eksponen. Literal floating-point dapat berbentuk desimal ataupun eksponensial.

Contoh: 

	3.14159       /* Legal */
	314159E-5L    /* Legal */
	510E          /* Illegal: incomplete exponent */
	210f          /* Illegal: no decimal or exponent */
	.e55          /* Illegal: missing integer or fraction */

## Konstanta Character 

Literal jenis character ditulis diantara tanda petik (SINGLE QUOTED), ` 'x' ` dan dapat disimpan dalam variabel tipe ` char `.

Literal character dapat berupa karakter biasa  ` 'x' `, atau sebuah **'escape sequence'** (berawal dengan tanda ` '\' `) seperti ` '\n' `, ` '\t' `, atau dapat juga berupa universal character seperti ` '\u02C0' `. 

Dalam bahasa C terdapat beberapa karakter yang memiliki arti khusus, seperti ` '\n' ` berarti tanda untuk ganti baris baru. Beberapa karakter khusus yang lain terdapat dalam tabel berikut ini: 

Karakter esc/khusus | Arti
--- | --- 
` \\ ` | karakter \ 
` \' ` | karakter ' 
` \" ` | karakter "
` \? ` | karakter ?
` \a ` | Alert or bell
` \b ` | Backspace 
` \f ` | Form feed
` \n ` | Newline
` \r ` | Carriage return
` \t ` | Horizontal tab
` \v ` | Vertical tab
` \ooo ` | Octal number of one to three digits
` \xhh . . . ` | Hexadecimal number of one or more digits

Berikut ini adalah contoh program menggunakan beberapa karakter khusus: 

	#include <stdio.h>
	
	int main()
	{
		printf("Hello\tWorld\n\n");
		return 0;
	}

## String literal

Literal jenis string ditulis diatanra tanda petik double (DOUBLE-QUOTED), ` "string" `. Sebuah string dapat mengandung karakter biasa, karakter khusus ataupun karakter universal.

Beberapa contoh string literal adalah sebagai berikut:

	"hello, dear"
	"hello, \
	dear"
	
	"hello, " "d" "ear"

## Mendefinisikan konstanta

Terdapat dua cara untuk mendefinisikan konstanta dalam bahasa C

1. menggunakan preprocessor  ` #define `, format ` #define identifier value `
2. menggunakan kata kunci ` const `, format ` const type variable = value; `

Berikut adalah contoh definisi konstanata menggunakan preprocessor.

	#include <stdio.h>
	#define LENGTH 10   
	#define WIDTH  5
	#define NEWLINE '\n'
	
	int main()
	{
		int area;
		
		area = LENGTH * WIDTH;
		printf("value of area : %d", area);
		printf("%c", NEWLINE);
		return 0;
	}

Contoh konstanta menggunakan katakunci ` const `

	#include <stdio.h>
	
	int main()
	{
		const int  LENGTH = 10;
		const int  WIDTH  = 5;
		const char NEWLINE = '\n';
		int area;
		
		area = LENGTH * WIDTH;
		printf("value of area : %d", area);
		printf("%c", NEWLINE);
		return 0;
	}

Dalam bahasa C, biasanya konstanta dibuat dengan huruf BESAR (CAPITAL)

# Operator

Operator adalah sebuah simbol untuk memerintahkan pada kompiler melakukan operasi matematika atau manipulasi logika. Terdapat banyak jenis operasi yang dapat digunakan dalam Bahasa C, antara lain:

* Operator **Aritmatika** (Arithmetic operators)
* Operator **Relasi/perbandingan** (Relational operators)
* Operator **Logika** (Logical operators)
* Operator **Bitwise** (Bitwise operators)
* Operator **Assigment** (assigment operators) 
* **Operator lainnya**

## Operator Arithmetic

Tabel berikut ini menunjukan semua simbol operator arithmetic yang terdapat dalam bahasa C.  Pada kolom paling kanan dianggap bahwa nilai ` A ` adalah ` 10 ` dan nilai ` B ` adalah ` 20 `.

Operator | Keterangan | Contoh
--- | --- | ---
` + `  | Menambahkan antara dua operan (variabel atau literal) | `A + B` menghasilkan `30`
` - ` | Mengurangi operan pertama dengan operan kedua | `A - B` menghasilkan `-10`
` * `| Perkalian antara dua operan | `A * B` menghasilkan `200`
` / ` | Membagi sebuah (operan sebelum simbol `/`) atau numerator dengan de-numerator (operan setelah simbol `/`) | `B / A` menghasilkan `2`
` % ` | Operator modulus, menghasilkan sisa hasil bagi dua operan  | `B % A`  menghasilkan `0`
` ++ ` | Opeartor increments menambah sebuah operan dengan angka satu | `A++` menghasilkan ` 11 `
` -- ` | Operator decrement mengurangi sebuah operan dengan angka 1 | ` A-- ` menghasilkan ` 9 `

Berikut adalah contoh kode program untuk membantu memahami semua operator arithmetic yang tersedia dalam bahasa C.

	#include <stdio.h>
	
	main()
	{
		int a = 21;
		int b = 10;
		int c ;
		
		c = a + b;
		printf("Line 1 - Value of c is %d\n", c );
		c = a - b;
		printf("Line 2 - Value of c is %d\n", c );
		c = a * b;
		printf("Line 3 - Value of c is %d\n", c );
		c = a / b;
		printf("Line 4 - Value of c is %d\n", c );
		c = a % b;
		printf("Line 5 - Value of c is %d\n", c );
		c = a++; 
		printf("Line 6 - Value of c is %d\n", c );
		c = a--; 
		printf("Line 7 - Value of c is %d\n", c );
		
	}

Jika dijalankan akan ditampilkan hasil sebagai berikut:

	Line 1 - Value of c is 31
	Line 2 - Value of c is 11
	Line 3 - Value of c is 210
	Line 4 - Value of c is 2
	Line 5 - Value of c is 1
	Line 6 - Value of c is 21
	Line 7 - Value of c is 22

## Relational Operator (Perbandingan)

Tabel berikut ini berisi daftar semua operator Relational yang terdapat dalam bahasa C. Pada kolom paling kanan dianggap bahwa `A` bernilai  ` 10 ` dan ` B ` bernilai ` 20 `.

Operator | Keterangan | Contoh
--- | --- | --- 
` == ` | Membandingkan pakah kedua operan (Variabel atau literal) memiliki nilai yang sama  | `(A == B)` hasilnya ` false `.
` != ` | Membandingkan apakah nilai kedua operan TIDAK SAMA | `(A != B)` hasilnya adalah ` true `.
` > ` | Membandingkan apakah operan kiri memiliki nilai lebih besar daripada operan kanan |  ` (A > B) ` hasilnya ` true `.
` < ` | Membandingkan apakah operan sebelah kiri memiliki nilai lebih kecil dibanding operan sebelah kanan |  ` (A < B) ` hasilnya adalah ` true `. 
` >= ` | Membandingkan apakah operan kiri LEBIH BESAR atau SAMA DENGAN operan kanan | ` (A >= B) ` hasilnya ` false `.
` <= ` | Membandignkan apakah operan kiri LEBIH KECIL atau SAMA DENGAN dibanding operan kanan | ` (A <= B) ` hasilnya adalah `true`.

Di bawah ini diberikan contoh program menggunakan operator relational (perbandingan) dan hasilnya

	#include <stdio.h>

	main()
	{
		int a = 21;
		int b = 10;
		int c ;
		
		if( a == b )
		{
			printf("Line 1 - a SAMA DENGAN b\n" );
		} else {
			printf("Line 1 - a TIDAK SAMA DENGAN b\n" );
		}
		
		if ( a < b )
		{
			printf("Line 2 - a LEBIH KECIL b\n" );
		} else {
			printf("Line 2 - a TIDAK LEBIH KECIL DARI b\n" );
		}
		
		if ( a > b )
		{
			printf("Line 3 - a LEBIH BESAR b\n" );
		} else {
			printf("Line 3 - a TIDAK LEBIH BESAR DARI b\n" );
		}
		
		/* Sekarang nilai untuk a dan b diubah*/
		a = 5;
		b = 20;
		
		if ( a <= b )
		{
			printf("Line 4 - a LEBIH KECIL atau SAMA DENGAN  b\n" );
		}
		if ( b >= a )
		{
			printf("Line 5 - b LEBIH BESAR atau SAMA DENGAN b\n" );
		}
	}


Hasilnya: 

	Line 1 - a TIDAK SAMA DENGAN b
	Line 2 - a TIDAK LEBIH KECIL b
	Line 3 - a LEBIH BESAR DARI b
	Line 4 - a LEBIH KECIL atau SAMA DENGAN  b
	Line 5 - b LEBIH BESAR atau SAMA DENGAN b

## Operator Logical (perbandingan secara BINARY)

Berikut ini adalah tabel yang berisi daftar semua operator logical yang terdapat dalam bahasa C: Pada kolom paling kanan dianggap bahwa ` A ` bernilai 10 dan ` B ` bernilai 20.

Operator | Keterangan | Contoh
--- | --- | --- 
` && ` | Memanggil operator AND (&). Jika kedua operan tidak sama dengan NOL akan menghasilkan nilai ` true ` | ` (A && B) ` menghasilkan ` false `.
` || ` | Memanggil operator OR ( `|` ). Jika ada salah satu operan tidak sama dengan nol akan menghasilkan ` true `  |  ` (A || B) ` hasilnya ` true `. 
` ! ` | Memanggil operator NOT. Hasilnya merupakan kebalikan dari nilai binary yang terdapat di belakang operator | ` !(A && B) ` menghasilkan ` false `.

Berikut ini adalah contoh kode program dan hasilnya:

	#include <stdio.h>
	main()
	{
		int a = 5;
		int b = 20;
		int c ;
		
		if ( a && b )
		{
			printf("Line 1 - Hasilnya TRUE\n" );
		}
   
		if ( a || b )
		{
			printf("Line 2 - Hasilnya TRUE\n" );
		}
   
		/* lets change the value of  a and b */
		a = 0;
		b = 10;
		
		if ( a && b )
		{
			printf("Line 3 - Hasilnya TRUE\n" );
		} else {
			printf("Line 3 - Hasilnya FALSE\n" );
		}
		
		if ( !(a && b) )
		{
			printf("Line 4 - Hasilnya TRUE\n" );
		}
	}

Hasilnya:

	Line 1 - Hasilnya TRUE
	Line 2 - Hasilnya TRUE
	Line 3 - Hasilnya FALSE
	Line 4 - Hasilnya TRUE


## Operator Bitwise (operasi dalam bilangan biner)

Bitwise operator digunakan dalam bilangan biner dan beroperasi secara bit (angka terkecil dalam bilangan biner) demi bit. Tabel kebenaran (tabel operasi) dari tiga operator bitwise, `& (AND)`, `| (OR)` dan `^ (XOR)`, ` ~ (NOT) ` adalah sebagai berikut:

Tabel kebenaran operasi logika

p | q |  p & q | p OR q | p ^ q 
--- | --- | --- | --- | ---
0 | 0 | 0 | 0 | 0
0 | 1 | 0 | 1 | 1
1 | 1 | 1 | 1 | 0
1 | 0 | 0 | 1 | 1

dengan menganggap bahwa variabel  ` A = 60 ` dan ` B = 9 `, maka dalam bentuk bilangan biner akan berupa angka biner sebagai berikut:

	A = 0011 1100
	B = 0000 1001
	-----------------
	A&B = 0000 1000
	A|B = 0011 1101
	A^B = 0011 0101
	~A  = 1100 0011

Tabel berikut ini adalah daftar semua operator Bitwise dalam bahasa C. Pada kolom paling kanan dianggap bahwa ` A ` bernilai 60 dan ` B ` bernilai 13. Simbol untuk operasi ` OR ` adalah ` | `.

Operator | Keterangan | Contoh 
--- | --- | ---
` & ` | melakukan operasi AND | ` (A & B) ` menghasilkan ` 12 ` dalam biner ` 0000 1100 `
` | ` | Melakukan operasi OR. | ` (A|B) ` menghasilkan ` 61 ` dalam biner ` 0011 1101 `
` ^ ` | Melkaukan operasi XOR  | ` (A ^ B) ` menghasilkan ` 49 ` dalam biner ` 0011 0001 `
` ~ ` | Melkaukan operasi NOT  | ` (~A ) ` menghasilkan ` -61 ` dalam biner ` 1100 0011 `.
` << ` | Melakukan operasi GESER / SHIFT ke kiri sebanyak angka yang ditunjukan oleh operan kanan  | ` A << 2 ` menghasilkan ` 240 ` dalam biner ` 1111 0000 `
` >> ` | Melakukan operasi GESER ke kanan sebanyak angka yang ditunjukan oleh operan kanan |  ` A >> 2 ` menghasilkan ` 15 ` dalam biner ` 0000 1111 `

Dibawah oini adalah contoh program dan hasilnya:

	#include <stdio.h>
	
	main()
	{
		unsigned int a = 60;	/* 60 = 0011 1100 */
		unsigned int b = 13;	/* 13 = 0000 1101 */
		int c = 0;
		
		c = a & b;       /* 12 = 0000 1100 */ 
		printf("Line 1 - Value of c is %d\n", c );
		c = a | b;       /* 61 = 0011 1101 */
		printf("Line 2 - Value of c is %d\n", c );
		c = a ^ b;       /* 49 = 0011 0001 */
		printf("Line 3 - Value of c is %d\n", c );
		c = ~a;          /*-61 = 1100 0011 */
		printf("Line 4 - Value of c is %d\n", c );
		c = a << 2;     /* 240 = 1111 0000 */
		printf("Line 5 - Value of c is %d\n", c );
		c = a >> 2;     /* 15 = 0000 1111 */
		printf("Line 6 - Value of c is %d\n", c );
	}

Hasilnya:

	Line 1 - Value of c is 12
	Line 2 - Value of c is 61
	Line 3 - Value of c is 49
	Line 4 - Value of c is -61
	Line 5 - Value of c is 240
	Line 6 - Value of c is 15

## Operator Assigment

Tabel berikut berisi semua daftar operator assignment dalam bahasa C

Operator | Keterangan | Example
--- | --- | --- 
` = ` | Operator assigment sederhana, memasukan nilai ke variabel yang terletak di sebelah kiri operator | ` C = A + B ` menghasilkan nilai `A + B` disimpan dalam ` C `.
` += ` | Menambahkan nilai operan kiri (variabel) dengan operan kanan, dan hasilnya disimpan pada operan kiri.  | ` C += A ` sama dengan operasi ` C = C + A `.
` -= ` | Mengurangi operan kiri dengan operan kanan, hasilknya diismpan dalam operan kiri | ` C -= A ` serupa dengan oeprasi ` C = C - A `.
` *= ` | Mengalikan operan kiri dengan operan kanan, hasilnya disimpan dalam operan kiri,  | ` C *= A ` seruap dengan operasi ` C = C * A `
` /= ` | Membagi operan kiri dengan operan kanan, hasilnya disimpan dalam operan kiri | ` C /= A ` serupa dengan operasi ` C = C / A `.
` %= ` | Melakukan operasi modulus antara operan kiri dan operan kanan, hasilnya disimpan dalam operan kiri.  | ` C %= A ` serupa dengan operasi ` C = C % A `
` <<= ` | Melakukan operasi GESER bit terhadap operan kiri sebanyak operan kanan, hasilnya disimpan dalam operan kiri  | ` C <<= 2 ` serupa dengan operasi ` C = C << 2 ` 
` >>= ` | Melakukan operasi GESER kanan sebanyak operan kanan pada operan kiri, hasilnya disimpan dalam operan kiri,  | ` C >>= 2 ` serupa dengan operasi ` C = C >> 2 `
` &= ` | Melakukan operasi AND hasilnya disimpan di operan kiri  | ` C &= 2 ` serupa dengan operasi ` C = C & 2 `
` ^= ` | MElakukan operasi XOR hasilnya disimpan dalam operan kiri  | ` C ^= 2 ` seruap dengan operasi ` C = C ^ 2 '
` |= ` | Melakukan operasi OR hasilnya disimpan dalam operan kiri. | ` C |= 2 ` serupa dengan ` C = C | 2 `

Note: dalam baris terakhir pada tabel di atas ... operasi OR seharusnya digantikan dengan simbol ` | `

Di bawah ini adalah contoh program penggunakan operator assigment dan hasilnya:

	#include <stdio.h>
	main()
	{
		int a = 21;
		int c ;
		
		c =  a;
		printf("Line 1 - =  Operator Example, Value of c = %d\n", c );
		
		c +=  a;
		printf("Line 2 - += Operator Example, Value of c = %d\n", c );
		
		c -=  a;
		printf("Line 3 - -= Operator Example, Value of c = %d\n", c );
		
		c *=  a;
		printf("Line 4 - *= Operator Example, Value of c = %d\n", c );
		
		c /=  a;
		printf("Line 5 - /= Operator Example, Value of c = %d\n", c );
		
		c  = 200;
		c %=  a;
		printf("Line 6 - %= Operator Example, Value of c = %d\n", c );
		
		c <<=  2;
		printf("Line 7 - <<= Operator Example, Value of c = %d\n", c );
		
		c >>=  2;
		printf("Line 8 - >>= Operator Example, Value of c = %d\n", c );
		
		c &=  2;
		printf("Line 9 - &= Operator Example, Value of c = %d\n", c );
		
		c ^=  2;
		printf("Line 10 - ^= Operator Example, Value of c = %d\n", c );
		
		c |=  2;
		printf("Line 11 - |= Operator Example, Value of c = %d\n", c );
	}


Hasilnya:

	Line 1 - =  Operator Example, Value of c = 21
	Line 2 - += Operator Example, Value of c = 42
	Line 3 - -= Operator Example, Value of c = 21
	Line 4 - *= Operator Example, Value of c = 441
	Line 5 - /= Operator Example, Value of c = 21
	Line 6 - %= Operator Example, Value of c = 11
	Line 7 - <<= Operator Example, Value of c = 44
	Line 8 - >>= Operator Example, Value of c = 11
	Line 9 - &= Operator Example, Value of c = 2
	Line 10 - ^= Operator Example, Value of c = 0
	Line 11 - |= Operator Example, Value of c = 2

## Operator lainnya (sizeof & ternary)

Terdapat beberapa operator spesial dalam bahasa C, antara lain adalah ` sizeof ` dan  ` ? `, daftar selengkapnya terdapat dalam tabel berikut ini:

Operator | Keterangan | Contoh 
--- | --- | --- 
` sizeof() ` | Menghasilkan jumlah byte dalam memori untuk menyimpan variabel | ` sizeof(a) `, jika variabel ` a ` adalah integer, maka akan dihasilkan angka ` 4 `.
` & ` | Mengehasilkan alamt memori sebuah variabel. | ` &a; ` akan menghasilkan alamat memori variabel ` a `  dalam memori 
` * ` | Poiter pada sebuah variabel | ` *a;  ` menghasilkan sebuah variabel pointer ` a ` yang menunjuk pada sebuah tipe data tertentu, tipe data sesuai dengan dekalrasi variabel awal.
` ? : ` | Ekspresi kondisional  | `(ekspresi)?X=1:X=3; ` Jika ekspresi benar maka ` X = 1 `, sebaliknya ` X = 3 `.

Di bawah ini diberikan contoh program penggunaan operator spesial dan hasilnya:

	#include <stdio.h>
	
	main()
	{
		int a = 4;
		short b;
		double c;
		int* ptr;
		
		/* example of sizeof operator */
		printf("Line 1 - Size of variable a = %d\n", sizeof(a) );
		printf("Line 2 - Size of variable b = %d\n", sizeof(b) );
		printf("Line 3 - Size of variable c= %d\n", sizeof(c) );
		
		/* example of & and * operators */
		ptr = &a;	/* 'ptr' now contains the address of 'a'*/
		printf("value of a is  %d\n", a);
		printf("*ptr is %d.\n", *ptr);
		
		/* example of ternary operator */
		a = 10;
		b = (a == 1) ? 20: 30;
		printf( "Value of b is %d\n", b );
		
		b = (a == 10) ? 20: 30;
		printf( "Value of b is %d\n", b );
	}
	
Hasilnya:

	value of a is  4
	*ptr is 4.
	Value of b is 30
	Value of b is 20

## Urutan prioritas eksekusi (Presedence) operator 

Operator precedence menentukan bagaimana sebuah ekspresi dievaluasi. Operator-operator tertentu memiliki prioritas tinggi dibanding yang lain. Sebagai contoh, operator perkalian ` (*) ` memiliki prioritas lebih tinggi dibanding ` + `. 

Sebagai contoh statement berikut ` x=6+3*2; ` akan menghasilkan nilai ` 12 `, bukan ` 18 `, karena operator ` * ` memiliki prioritas lebih tinggi dibanding operator ` + `, sehingga pertama akan dilakukan perkalian ` 3*2 ` dan hasilknya akan di tambah dengan ` 6 `.

Berikut ini adalah daftar prioritas operator dalam bahasa C

Kategori | Operator | Urutan proses 
--- | --- | ---
Postfix | ` () [] -> . ++ -- ` | dari kiri ke kanan
Unary | ` + - ! ~ ++ - - (type)* & sizeof ` | dari kanan ke kiri 
Multiplicative | ` * / %  ` | dari kiri ke kanan 
Additive | ` + - ` | dari kiri ke kanan
Shift | ` << >> ` | dari kiri ke kanan
Relational | ` < <= > >= ` | dari kiri ke kanan 
Equality | ` == != ` | dari kiri ke kanan
Bitwise AND | ` & ` | dari kiri ke kanan
Bitwise XOR | ` ^ ` | dari kiri ke kanan
Bitwise OR | ` | ` | dari kiri ke kanan
Logical AND | ` && ` | dari kiri ke kanan
Logical OR | ` ||  ` | dari kiri ke kanan
Conditional | ` ?: ` | dari kanan ke kiri
Assignment | ` = += -= *= /= %=>>= <<= &= ^= |= ` | dari kanan ke kiri 
Comma | ` , ` |	Left to right 

Di bawah ini adalah contoh program untuk menunjukkan beberapa kasus prioritas operator dalam bahasa C, dan hasilnya:

	#include <stdio.h>
	
	main()
	{
		int a = 20;
		int b = 10;
		int c = 15;
		int d = 5;
		int e;
		
		e = (a + b) * c / d;      // ( 30 * 15 ) / 5
		printf("Value of (a + b) * c / d is : %d\n",  e );
		e = ((a + b) * c) / d;    // (30 * 15 ) / 5
		printf("Value of ((a + b) * c) / d is  : %d\n" ,  e );
		e = (a + b) * (c / d);   // (30) * (15/5)
		printf("Value of (a + b) * (c / d) is  : %d\n",  e );
		e = a + (b * c) / d;     //  20 + (150/5)
		printf("Value of a + (b * c) / d is  : %d\n" ,  e );
		
		return 0;
		
	}
	
Hasil:

	Value of (a + b) * c / d is : 90
	Value of ((a + b) * c) / d is  : 90
	Value of (a + b) * (c / d) is  : 90
	Value of a + (b * c) / d is  : 50
	









