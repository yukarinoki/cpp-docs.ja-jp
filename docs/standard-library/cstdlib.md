---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 70e05ad734fa49ba8cb96e4bf83bc05b99c5f55c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246525"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

標準 C ライブラリ ヘッダーが含まれています\<stdlib.h > を関連する名前を追加し、`std`名前空間。 外部リンケージを使用して、C 標準ライブラリ ヘッダーで宣言された名前を宣言することにより、このヘッダーを含む、`std`名前空間。

> [!NOTE]
> \<stdlib.h > 型が含まれていない**wchar_t**します。

## <a name="requirements"></a>必要条件

**ヘッダー**: \<cstdlib >

**名前空間:** std

## <a name="namespace-and-macros"></a>Namespace とマクロ

```cpp
namespace std {
    using size_t = see definition;
    using div_t = see definition;
    using ldiv_t = see definition;
    using lldiv_t = see definition;
}

#define NULL
#define EXIT_FAILURE
#define EXIT_SUCCESS
#define RAND_MAX
#define MB_CUR_MAX
```

## <a name="exposition-only-functions"></a>説明をわかりやすくのみ関数

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>開始と終了関数

|関数|説明|
|-|-|
|[_Exit](#_exit)|デストラクターまたは登録済みの関数を使用せず、プログラムを終了します。|
|[abort](#abort)|デストラクターを使用せずにプログラムを終了します。|
|[atexit](#atexit)|プログラムの終了の関数を登録します。|
|[exit](#exit)|スレッドおよび静的ストレージ、しを返します。 コントロールを持つオブジェクトを破棄します。|
|[at_quick_exit](#at_quick_exit)|プログラムの終了の引数を指定せず関数を登録します。|
|[quick_exit](#quick_exit)|プログラムの終了の保存されたオブジェクトをレジスタ関数。|
|[getenv](#getenv)|C 標準ライブラリのリファレンスを参照してください。|
|[system](#system)|C 標準ライブラリのリファレンスを参照してください。|

### <a name="_exit"></a> _Exit 関数

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Remarks

自動のオブジェクト、スレッド、または静的ストレージ存続期間のデストラクターの実行とに渡される関数を呼び出すことがなく、プログラムが終了`atexit()`します。 関数は、`_Exit`シグナル セーフです。

### <a name="abort"></a> 中止

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Remarks

自動のオブジェクト、スレッド、または静的ストレージ存続期間のデストラクターの実行とに渡される関数を呼び出すことがなく、プログラムが終了`atexit()`します。 関数は、`abort`シグナル セーフです。

### <a name="at_quick_exit"></a> at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>戻り値

登録が成功すると、0 以外の場合、失敗した場合は 0 します。

#### <a name="remarks"></a>Remarks

`at_quick_exit()`関数によって示される関数を登録する*func*引数を指定せずに呼び出されるときに`quick_exit`が呼び出されます。 指定されていないかどうかを呼び出す`at_quick_exit()`に対するすべての呼び出しの前に自動的に開かない`quick_exit`は成功と`at_quick_exit()`関数はデータの競合を導入していません。 登録の順序は不確定でない可能性がある場合`at_quick_exit`が 1 つのスレッドとしているので複数から呼び出された`at_quick_exit`登録は異なる、`atexit`登録、アプリケーションで両方の登録関数を呼び出す必要があります、同じ引数。 実装では、少なくとも 32 関数の登録がサポートされます。

### <a name="atexit"></a> atexit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Remarks

`atexit()`関数によって示される関数を登録する*func*通常のプログラムの終了時に引数を指定せずに呼び出されます。 指定されていないかどうかを呼び出す`atexit()`を呼び出す前に自動的に開かない`exit()`は成功と`atexit()`関数はデータの競合を導入していません。実装では、少なくとも 32 関数の登録がサポートされます。

#### <a name="return-value"></a>戻り値

登録は成功、失敗した場合は 0 以外の場合は、0 を返します。

### <a name="exit"></a> 終了

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Remarks

最初に、スレッド ストレージ存続期間を持つオブジェクトし、現在に関連付けられているスレッドは破棄されます。

次に、静的ストレージ存続期間を持つオブジェクトが破棄され、関数を呼び出すことによって登録`atexit`と呼ばれます。 呼び出しの結果に自動オブジェクトが破棄されない`exit()`します。 コントロールによって呼び出される登録済みの関数が抜ける場合`exit`関数がスローされた例外のハンドラーを提供しないため、`std::terminate()`呼び出されます。 登録されるたびの関数が呼び出されます。 自動ストレージ存続期間を持つオブジェクトはすべて、プログラムのメイン関数に持つ自動オブジェクトが含まれていないと、呼び出しを実行しますで破棄`exit()`します。 コントロールは、main でキャッチされた例外をスローすることによって、このような main 関数に直接転送できます。

次に、すべての開いているストリームの C (で宣言された関数のシグネチャによって仲介として<cstdio>) はフラッシュ、開いているすべてが C のストリームを閉じ、およびすべてのファイルで呼び出すことによって作成バッファー内のデータが書き込まれていないと`tmpfile()`が削除されます。

最後に、コントロールは、ホスト環境に返されます。 状態 0、EXIT_SUCCESS、実装で定義された形式の状態、正常に終了が返されます。 状態が EXIT_FAILURE の場合は、実装で定義された形式の状態の失敗の終了が返されます。 それ以外の場合返される状態は、実装定義です。

### <a name="getenv"></a> getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a> quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Remarks

呼び出しによって登録されている関数`at_quick_exit`が既に登録された時点で呼び出された関数がいずれかに登録した後、関数が呼び出されたものとする点を除いて、登録の逆順で呼び出されます。 オブジェクトは、呼び出しの結果は破棄されません`quick_exit`します。 コントロールによって呼び出される登録済みの関数が抜ける場合`quick_exit`関数がスローされた例外のハンドラーを提供しないため、`std::terminate()`呼び出されます。 使用して、関数が登録されている`at_quick_exit`を呼び出すスレッドによって呼び出される`quick_exit`、スレッド ストレージ存続期間を持つオブジェクトの id は使用しないでください、登録されている 1 つが登録されてそのための関数よりも、別のスレッドがあることができます。 登録済みの関数を呼び出した後`quick_exit`を呼び出さなければいけない`_Exit(status)`します。 標準のファイル バッファーをフラッシュされません。 関数は、`quick_exit`シグナル セーフは、関数は、登録されている場合`at_quick_exit`されます。

### <a name="system"></a> システム

```cpp
int system(const char* string);
```

## <a name="memory-allocation-functions"></a>メモリ割り当て関数

```cpp
void* aligned_alloc(size_t alignment, size_t size);
void* calloc(size_t nmemb, size_t size);
void free(void* ptr);
void* malloc(size_t size);
void* realloc(void* ptr, size_t size);
double atof(const char* nptr);
int atoi(const char* nptr);
long int atol(const char* nptr);
long long int atoll(const char* nptr);
double strtod(const char* nptr, char** endptr);
float strtof(const char* nptr, char** endptr);
long double strtold(const char* nptr, char** endptr);
long int strtol(const char* nptr, char** endptr, int base);
long long int strtoll(const char* nptr, char** endptr, int base);
unsigned long int strtoul(const char* nptr, char** endptr, int base);
unsigned long long int strtoull(const char* nptr, char** endptr, int base);
```

#### <a name="remarks"></a>Remarks

これらの関数は、C 標準ライブラリで指定されたセマンティクスを持ちます。

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>マルチバイトまたはワイド文字列と文字の変換関数

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>Remarks

これらの関数は、C 標準ライブラリで指定されたセマンティクスを持ちます。

## <a name="algorithm-functions"></a>アルゴリズム関数

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>Remarks

これらの関数は、C 標準ライブラリで指定されたセマンティクスを持ちます。

## <a name="low-quality-random-number-generation-functions"></a>低品質のランダムな数値生成関数

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>Remarks

これらの関数は、C 標準ライブラリで指定されたセマンティクスを持ちます。

## <a name="absolute-values"></a>絶対値

```cpp
int abs(int j);
long int abs(long int j);
long long int abs(long long int j);
float abs(float j);
double abs(double j);
long double abs(long double j);
long int labs(long int j);
long long int llabs(long long int j);
div_t div(int numer, int denom);
ldiv_t div(long int numer, long int denom);
lldiv_t div(long long int numer, long long int denom);
ldiv_t ldiv(long int numer, long int denom);
lldiv_t lldiv(long long int numer, long long int denom);
```

### <a name="remarks"></a>Remarks

これらの関数は、C 標準ライブラリで指定されたセマンティクスを持ちます。

## <a name="functions"></a>関数

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
