---
title: _set_se_translator | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d4a5c9e86023ea47f23b648cad1a4dffedf905b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411521"
---
# <a name="setsetranslator"></a>_set_se_translator

スレッドごとのコールバック関数を C Win32 例外 (C 構造化例外) を変換する型指定例外に設定します。

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

によって登録されている以前の変換関数へのポインターを返します **_set_se_translator**、前の関数を後で復元できるようにします。 Previous 関数が設定されていない場合、戻り値を使用して、既定の動作を復元することができます。この値は、 **nullptr**です。

## <a name="remarks"></a>コメント

**_Set_se_translator**関数として C++ Win32 例外 (C 構造化例外) を処理する方法を提供する例外を入力します。 C++ で処理するそれぞれの C 例外を許可する**キャッチ**ハンドラー、まず使用、または C の例外への特定のクラス型の属性から派生できる C 例外のラッパー クラスを定義します。 このクラスを使用するには、C 例外が発生するたびに内部例外処理メカニズムによって呼び出されるカスタム C 例外変換関数をインストールします。 照合 C によってキャッチできる型の例外をスローする、トランスレーター関数内で**キャッチ**ハンドラー。

使用する必要があります[/EHa](../../build/reference/eh-exception-handling-model.md)を使用する場合 **_set_se_translator**です。

カスタム変換関数を指定するには、呼び出す **_set_se_translator**変換関数の名前、引数として使用します。 記述する変換関数を持つスタックの関数呼び出しごとに 1 回呼び出されます**再試行**ブロックします。 既定の変換関数はありません。

変換関数は、C++ 型の例外をスローする以外のことは何もすべきではありません。 スローに加えて何かを行う場合 (たとえば、ログ ファイルへの書き込みなど)、プログラムが期待どおりに動作しない可能性があります。それは、変換関数が呼び出される回数がプラットフォームに依存するためです。

マルチスレッド環境では、変換関数は各スレッドとは別に管理されます。 新しい各スレッドは、それぞれの変換関数をインストールする必要があります。 したがって、各スレッドが、それぞれの変換処理を担当します。 **_set_se_translator**は 1 つのスレッドに固有の別の DLL が別の変換関数をインストールできます。

*SeTransFunction*を記述する関数は、(/clr でコンパイルされません)、ネイティブ コンパイルされた関数をする必要があります。 Win32 する、符号なし整数およびポインターもする必要がありますかかる **_EXCEPTION_POINTERS**引数として構造体。 引数は、Win32 API への呼び出しの戻り値**GetExceptionCode**と**GetExceptionInformation**関数、それぞれします。

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

**_Set_se_translator**、CRT に動的にリンクするときに影響がある。 プロセス内の DLL を呼び出す可能性があります別 **_set_se_translator** 、ハンドラーを独自に置き換えます。

使用する場合 **_set_se_translator**からマネージ コード (/clr と共にコンパイルされたコード) またはネイティブおよびマネージ コード、トランスレーターがネイティブ コードのみで生成される例外を決まることに注意します。 マネージ コードで生成されるマネージ例外 (`System::Exception` の発生時のものなど) はいずれも、変換関数経由ではルーティングされません。 Win32 関数を使用してマネージ コードで発生した例外**RaiseException**または変換プログラム経由でルーティングは、0 除算例外などのシステム例外によって発生します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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

class SE_Exception
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

によって提供される機能が **_set_se_translator**はマネージ コードでは使用できない、行うことが場合でも、ネイティブ コードは コンパイル時に、ネイティブ コードでこのマッピングを使用して、 **/clr**切り替えるを使用して、ネイティブ コードに示されている限り、`#pragma unmanaged`です。 生成し、例外を処理するコードをマークする必要がありますマップするのには、マネージ コードでは、構造化例外がスローされた場合はされている、`#pragma unmanaged`です。 次のコードは考えられる使用法を示しています。 詳細については、「[プラグマ ディレクティブと __Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class CMyException{
private:
    unsigned int nSE;
public:
    CMyException() : nSE{ 0 } {}
    CMyException(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw CMyException(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(CMyException e)
    {
        printf("Caught CMyException.\n");
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
Caught CMyException, error c0000094
```

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
