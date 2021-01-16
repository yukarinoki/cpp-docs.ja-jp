---
description: '詳細については、次を参照してください: _set_se_translator'
title: _set_se_translator
ms.date: 1/14/2021
api_name:
- _set_se_translator
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_se_translator
- set_se_translator
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
ms.openlocfilehash: bde7b716bcb69f38ba6ab64151e2ec4fe93e0c9c
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243008"
---
# `_set_se_translator`

Win32 例外 (C 構造化例外) を C++ の型指定された例外に変換するスレッドごとのコールバック関数を設定します。

## <a name="syntax"></a>構文

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>パラメーター

*`seTransFunction`*\
ユーザーが作成した C 構造化例外の変換関数へのポインター。

## <a name="return-value"></a>戻り値

は、 **`_set_se_translator`** 前の関数を後で復元できるように、によって登録された前の変換関数へのポインターを返します。 前の関数が設定されていない場合は、戻り値を使用して既定の動作を復元できます。この値にはを指定でき **`nullptr`** ます。

## <a name="remarks"></a>注釈

関数は、 **`_set_se_translator`** Win32 例外 (c 構造化例外) を C++ 型の例外として処理する方法を提供します。 各 C 例外が C++ ハンドラーによって処理されるようにするに **`catch`** は、まず、特定のクラス型を c 例外に属性化するために使用または派生できる c 例外ラッパークラスを定義します。 このクラスを使用するには、C 例外が発生するたびに内部例外処理メカニズムによって呼び出されるカスタム C 例外変換関数をインストールします。 変換関数内では、一致する C++ ハンドラーによってキャッチされる、型指定された例外をスローでき **`catch`** ます。

_Set_se_translator を使用する場合は、を使用する必要があり [`/EHa`](../../build/reference/eh-exception-handling-model.md) ます。 

カスタム変換関数を指定するには、 **`_set_se_translator`** 変換関数の名前を引数として使用してを呼び出します。 記述する変換関数は、ブロックを持つスタック上の関数呼び出しごとに1回呼び出され **`try`** ます。 既定の変換関数はありません。

変換関数は、C++ 型の例外をスローする以外のことは何もすべきではありません。 (たとえば、ログファイルへの書き込みなどで) スローに加えて何かを実行すると、変換関数が呼び出される回数がプラットフォームに依存しているため、プログラムが予期したとおりに動作しない可能性があります。

マルチスレッド環境では、変換関数は各スレッドとは別に管理されます。 新しい各スレッドは、それぞれの変換関数をインストールする必要があります。 したがって、各スレッドが、それぞれの変換処理を担当します。 **`_set_se_translator`** は、1つのスレッドに固有のもので、別の DLL で別の変換関数をインストールできます。

記述する *Setransfunction* 関数は、ネイティブコンパイル関数 (/clr でコンパイルされません) である必要があります。 引数として、符号なし整数と Win32 構造体へのポインターを受け取る必要があり **`_EXCEPTION_POINTERS`** ます。 引数は、それぞれ Win32 API および関数への呼び出しの戻り値 **`GetExceptionCode`** **`GetExceptionInformation`** です。

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

**_Set_se_translator** の場合、CRT に動的にリンクするときには影響があります。プロセス内の別の DLL が **_set_se_translator** を呼び出し、ハンドラーをそれ自体のに置き換える場合があります。

マネージコード (/clr でコンパイルされたコード) または混合ネイティブコードまたはマネージコードから **_set_se_translator** を使用する場合は、変換プログラムがネイティブコードでのみ生成される例外に影響することに注意してください。 マネージコードで生成されたマネージ例外 (発生する場合など `System::Exception` ) は、変換関数によってルーティングされません。 Win32 関数 **RaiseException** を使用してマネージコードで発生した例外や、ゼロ除算例外などのシステム例外によって発生した例外は、変換プログラムを通じてルーティングされます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_set_se_translator**|\<eh.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example-catch-__try-exception-error"></a>例: キャッチ __try 例外エラー

このサンプルでは、の呼び出しをラップして、構造化例外変換器を設定し、RAII クラスで古いものを復元し `Scoped_SE_Translator` ます。 このクラスを使用すると、スコープ固有の変換を1つの宣言として導入できます。 クラスデストラクターは、コントロールがスコープから外れたときに元のトランスレーターを復元します。

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
    const unsigned int nSE;
public:
    SE_Exception() noexcept : SE_Exception{ 0 } {}
    SE_Exception( unsigned int n ) noexcept : nSE{ n } {}
    unsigned int getSeNumber() const noexcept { return nSE; }
};

class Scoped_SE_Translator
{
private:
    const _se_translator_function old_SE_translator;
public:
    Scoped_SE_Translator( _se_translator_function new_SE_translator ) noexcept
        : old_SE_translator{ _set_se_translator( new_SE_translator ) } {}
    ~Scoped_SE_Translator() noexcept { _set_se_translator( old_SE_translator ); }
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

void trans_func( unsigned int u, EXCEPTION_POINTERS* )
{
    throw SE_Exception( u );
}

int main()
{
    Scoped_SE_Translator scoped_se_translator{ trans_func };
    try
    {
        SEFunc();
    }
    catch( const SE_Exception& e )
    {
        printf( "Caught a __try exception, error %8.8x.\n", e.getSeNumber() );
    }
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example-catch-se_exception-error"></a>例: キャッチ SE_Exception エラー

**_Set_se_translator** によって提供される機能はマネージコードでは使用できませんが、ネイティブコードが **/clr** スイッチの下のコンパイルに含まれていても、ネイティブコードがを使用して示されている限り、ネイティブコードでこのマッピングを使用でき `#pragma unmanaged` ます。 構造化例外が、マップされるマネージコードでスローされている場合は、例外を生成して処理するコードをとしてマークする必要があり `#pragma unmanaged` ます。 次のコードは考えられる使用法を示しています。 詳細については、「[プラグマ ディレクティブと __Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <stdio.h>
#include <exception>

int thrower_func( int i ) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception
{
private:
    const unsigned int nSE;
public:
    SE_Exception() noexcept : SE_Exception{ 0 } {}
    SE_Exception( unsigned int n ) noexcept : nSE{ n } {}
    unsigned int getSeNumber() const noexcept { return nSE; }
};

class Scoped_SE_Translator
{
private:
    const _se_translator_function old_SE_translator;
public:
    Scoped_SE_Translator( _se_translator_function new_SE_translator ) noexcept
        : old_SE_translator{ _set_se_translator( new_SE_translator ) } {}
    ~Scoped_SE_Translator() noexcept { _set_se_translator( old_SE_translator ); }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS )
{
    throw SE_Exception( u );
}

void DoTest()
{
    try
    {
        thrower_func( 10 );
    }
    catch( const SE_Exception& e )
    {
        printf( "Caught SE_Exception, error %8.8x\n", e.getSeNumber() );
    }
    catch(...)
    {
        printf( "Caught unexpected SEH exception.\n" );
    }
}
#pragma managed

int main() {
    Scoped_SE_Translator scoped_se_translator{ my_trans_func };

    DoTest();
}
```

```Output
Caught SE_Exception, error c0000094
```

## <a name="see-also"></a>参照

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)\
[`set_terminate`](set-terminate-crt.md)\
[`set_unexpected`](set-unexpected-crt.md)\
[`terminate`](terminate-crt.md)\
[`unexpected`](unexpected-crt.md)\
