---
title: qsort_s
ms.date: 4/2/2020
api_name:
- qsort_s
- _o_qsort_s
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- qsort_s
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
ms.openlocfilehash: 6013098199e1b69d03dc9cf2780cbf4376abcc0d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332975"
---
# <a name="qsort_s"></a>qsort_s

クイック ソートを実行します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [qsort](qsort.md) です。

## <a name="syntax"></a>構文

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>パラメーター

*base*<br/>
対象となる配列の先頭。

*数*<br/>
配列サイズ (要素数)。

*幅*<br/>
要素のサイズ (バイト単位)。

*比較*<br/>
比較関数。 最初の引数は*コンテキスト*ポインタです。 2 番目の引数は、検索用の*キー*へのポインターです。 3 番目の引数は *、key*と比較する配列要素へのポインターです。

*context*<br/>
*比較*ルーチンがアクセスする必要がある任意のオブジェクトを指定できるコンテキストへのポインター。

## <a name="remarks"></a>解説

**qsort_s**関数は、*数値要素の*配列を並べ替えるクイックソートアルゴリズムを*実装します。* 引数*の base*は、並べ替えられる配列のベースへのポインターです。 **qsort_s、** この配列を並べ替えられた要素で上書きします。 引数*compare*は、2 つの配列要素を比較し、それらの関係を指定する値を返すユーザー提供ルーチンへのポインターです。 **qsort_s**は、ソート中に*比較*ルーチンを 1 回以上呼び出し、呼び出しごとに 2 つの配列要素へのポインターを渡します。

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

ルーチンは、要素を比較し、次の値のいずれかを返す必要があります。

|戻り値|説明|
|------------------|-----------------|
|< 0|**エレム1**未満**のエレム2**|
|0|**エレム2**に相当する**エレム**1|
|> 0|**エレム1**より大きい**2**|

配列は、比較関数による定義に従って、昇順で並べ替えられます。 配列を降順で並べ替えるには、比較関数の "より大きい" と "より小さい" の意味を入れ替えます。

この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は戻り **、errno**は**EINVAL**に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="error-conditions"></a>エラー条件

|key|base|compare|num|width|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**NULL**|any|any|any|any|**Einval**|
|any|**NULL**|any|!= 0|any|**Einval**|
|any|any|any|any|<= 0|**Einval**|
|any|any|**NULL**|any|any|**Einval**|

**qsort_s**は**qsort**と同じ動作を持ちますが、*コンテキスト*パラメータを持ち、 **errno**を設定します。 *コンテキスト*パラメーターを渡すことにより、比較関数はオブジェクト ポインターを使用して、オブジェクトの機能や、要素ポインターを介してアクセスできないその他の情報にアクセスできます。 *context*パラメーターを追加すると、静的変数を使用して共有情報を*比較*関数で利用できるようにすることで、*コンテキスト*を使用して再入可能なバグを回避できるため **、qsort_s**の安全性が高まります。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h > と \<search.h >|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:**[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のすべてのバージョンです。

## <a name="example"></a>例

qsort_s**関数で** *context*パラメーターを使用する方法を次の例に示します。 *context*パラメーターを使用すると、スレッド セーフな並べ替えを実行しやすくなります。 スレッド セーフを確保するために同期する必要がある静的変数を使用する代わりに、並べ替えごとに異なる*コンテキスト*パラメーターを渡します。 この例では、*コンテキスト*パラメーターとしてロケール オブジェクトが使用されます。

```cpp
// crt_qsort_s.cpp
// compile with: /EHsc /MT
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S in that codepage and \x00a4
// is the n tilde.

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.850"
#define SPANISH_LOCALE "Spanish_Spain.850"
#define ENGLISH_LOCALE "English_US.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S and \x001f for the n tilde.
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.1252"
#define SPANISH_LOCALE "Spanish_Spain.1252"
#define ENGLISH_LOCALE "English_US.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making sort_array vulnerable to thread
// conflicts.

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char s1[256];
    char s2[256];
    strcpy_s(s1, 256, *(char**)str1);
    strcpy_s(s2, 256, *(char**)str2);
    _strlwr_s( s1, sizeof(s1) );
    _strlwr_s( s2, sizeof(s2) );

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(s1,
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);

}

void sort_array(char *array[], int num, locale &loc)
{
    qsort_s(array, num, sizeof(char*), compare, &loc);
}

void print_array(char *a[], int c)
{
   for (int i = 0; i < c; i++)
      printf("%s ", a[i]);
   printf("\n");

}

void sort_german(void * Dummy)
{
   sort_array(array1, 6, locale(GERMAN_LOCALE));
}

void sort_spanish(void * Dummy)
{
   sort_array(array2, 3, locale(SPANISH_LOCALE));
}

void sort_english(void * Dummy)
{
   sort_array(array3, 3, locale(ENGLISH_LOCALE));
}

int main( )
{
   int i;
   HANDLE threads[3];

   printf("Unsorted input:\n");
   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);

   // Create several threads that perform sorts in different
   // languages at the same time.

   threads[0] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_german , 0, NULL));
   threads[1] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_spanish, 0, NULL));
   threads[2] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_english, 0, NULL));

   for (i = 0; i < 3; i++)
   {
      if (threads[i] == reinterpret_cast<HANDLE>(-1))
      {
         printf("Error creating threads.\n");
         exit(1);
      }
   }

   // Wait until all threads have terminated.
   WaitForMultipleObjects(3, threads, true, INFINITE);

   printf("Sorted output: \n");

   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);
}
```

### <a name="sample-output"></a>サンプル出力

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>関連項目

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
