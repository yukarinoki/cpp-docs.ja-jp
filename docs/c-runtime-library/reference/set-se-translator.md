---
title: _set_se_translator
ms.date: 02/21/2018
apiname:
- _set_se_translator
apilocation:
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
apitype: DLLExport
f1_keywords:
- _set_se_translator
- set_se_translator
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
ms.openlocfilehash: 18ee500d7b884d1934c29dc91d9bcb03d507680d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356551"
---
# <a name="setsetranslator"></a>_set_se_translator

C++ には、Win32 例外 (C 構造化例外) を変換するスレッドごとのコールバック関数の型指定例外を設定します。

## <a name="syntax"></a>構文

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>パラメーター

*seTransFunction*<br/>
ユーザーが作成した C 構造化例外の変換関数へのポインター。

## <a name="return-value"></a>戻り値

によって登録された前の変換関数へのポインターを返し **_set_se_translator**、前の関数を後で復元できるようにします。 既定の動作を復元する戻り値を使用できますの前の関数が設定されていない場合この値は**nullptr**します。

## <a name="remarks"></a>Remarks

**_Set_se_translator**関数として Win32 例外 (C 構造化例外) を処理する方法を提供するC++例外の型を指定します。 C++ で処理する C の例外を許可する**キャッチ**ハンドラーでは、まず、使用するかを C 例外の特定のクラス型の属性に由来する C 例外のラッパー クラスを定義します。 このクラスを使用するには、C 例外が発生するたびに内部例外処理メカニズムによって呼び出されるカスタム C 例外変換関数をインストールします。 一致する C++ でキャッチできる任意の型例外をスローする変換関数内で**キャッチ**ハンドラー。

使用する必要があります[/EHa](../../build/reference/eh-exception-handling-model.md)を使用する場合 **_set_se_translator**します。

カスタム変換関数を指定するには、呼び出す **_set_se_translator**引数として、変換関数の名前を使用します。 作成した変換関数を持つスタックの関数呼び出しごとに 1 回呼び出されます**お試しください**ブロックします。 既定の変換関数はありません。

変換関数は、C++ 型の例外をスローする以外のことは何もすべきではありません。 スローに加えて何かを行う場合 (たとえば、ログ ファイルへの書き込みなど)、プログラムが期待どおりに動作しない可能性があります。それは、変換関数が呼び出される回数がプラットフォームに依存するためです。

マルチスレッド環境では、変換関数は各スレッドとは別に管理されます。 新しい各スレッドは、それぞれの変換関数をインストールする必要があります。 したがって、各スレッドが、それぞれの変換処理を担当します。 **_set_se_translator** 1 つのスレッドに固有では別の DLL が別の変換関数をインストールできます。

*SeTransFunction*関数を記述する必要があります (/clr でコンパイルされません)、ネイティブ コンパイルされた関数。 Win32 に符号なし整数およびポインターをかかる必要があります **_EXCEPTION_POINTERS**引数として構造体。 引数は、Win32 API 呼び出しの戻り値では**GetExceptionCode**と**GetExceptionInformation**関数、それぞれします。

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

**_Set_se_translator**、CRT に動的にリンクするときに影響がある; プロセス内の DLL を呼び出す別 **_set_se_translator**ハンドラーを独自に置き換えます。

使用する場合 **_set_se_translator**マネージ コード (/clr でコンパイルされたコード) からでも、ネイティブおよびマネージ コードを混在トランスレーターがネイティブ コードのみで生成される例外を影響に注意してください。 マネージド コードで生成されるマネージド例外 (`System::Exception` の発生時のものなど) はいずれも、変換関数経由ではルーティングされません。 Win32 関数を使用してマネージ コードで発生する例外**RaiseException**トランスレーター経由、0 除算例外などのシステム例外が原因か。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_set_se_translator**|\<eh.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```cpp
// crt_settrans.cpp
// compile with: cl /W4 /EHa crt_settrans.cpp
#include <stdio.h>
#include <windows.h>
#include <eh.h>
#include <exception>

class SE_Exception : public std::exception
{
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception( unsigned int n ) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

void SEFunc()
{
    __try
    {
        printf( "In __try, about to force exception\n" );
        int x = 5;
        int y = 0;
        int *p = &y;
        *p = x / *p;
    }
    __finally
    {
        printf( "In __finally\n" );
    }
}

void trans_func(unsigned int u, EXCEPTION_POINTERS*)
{
    throw SE_Exception(u);
}

int main()
{
    auto original = _set_se_translator(trans_func);
    try
    {
        SEFunc();
    }
    catch(SE_Exception& e)
    {
        printf("Caught a __try exception, error %8.8x.\n", e.getSeNumber());
    }
    _set_se_translator(original);
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example"></a>例

によって提供される機能が **_set_se_translator**はマネージ コードでは使用できない、することができる場合でも、ネイティブ コードがコンパイル下では、ネイティブ コードでこのマッピングを使用して、 **/clr**切り替えるを使用してネイティブ コードが示される限り`#pragma unmanaged`します。 マップするのには、マネージ コードで、構造化例外がスロー、場合を生成し、例外を処理するコードをマークする必要があります`#pragma unmanaged`します。 次のコードは考えられる使用法を示しています。 詳細については、「[プラグマ ディレクティブと __Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>
#include <exception>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception {
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw SE_Exception(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(SE_Exception& e)
    {
        printf("Caught SE_Exception, error %8.8x\n", e.getSeNumber());
    }
    catch(...)
    {
        printf("Caught unexpected SEH exception.\n");
    }
}
#pragma managed

int main() {
    auto original = _set_se_translator(my_trans_func);
    DoTest();
    _set_se_translator(original);
}
```

```Output
Caught SE_Exception, error c0000094
```

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
