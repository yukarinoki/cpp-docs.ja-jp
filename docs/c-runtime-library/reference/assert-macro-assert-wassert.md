---
title: assert マクロ、_assert、_wassert
description: Assert マクロと関数が C ランタイムに与える影響。
ms.date: 11/04/2016
api_name:
- assert
- _assert
- _wassert
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
ms.openlocfilehash: 071424f2201ceda43438fe1056801811fe444a01
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609085"
---
# <a name="assert-macro-_assert-_wassert"></a>assert マクロ、_assert、_wassert

式を評価し、結果がの場合 **`false`** 、診断メッセージを出力し、プログラムを中止します。

## <a name="syntax"></a>構文

```C
assert(
   expression
);
void _assert(
   char const* message,
   char const* filename,
   unsigned line
);
void _wassert(
   wchar_t const* message,
   wchar_t const* filename,
   unsigned line
);
```

### <a name="parameters"></a>パラメーター

*式 (expression)*<br/>
0以外 ( **`true`** ) または 0 () に評価されるスカラー式 (ポインター式を含む) **`false`** 。

*message*<br/>
表示するメッセージ。

*ファイル名*<br/>
アサーションが失敗したソース ファイルの名前。

*line*<br/>
失敗したアサーションのソース ファイルの行番号。

## <a name="remarks"></a>解説

`assert` マクロは通常、プログラム開発中の論理エラーを識別するために使用されます。 予期しない条件が発生したときにプログラムの実行*expression*を停止するに **`false`** は、プログラムが正しく動作していないときにのみに評価されるように expression 引数を実装します。 マクロ **NDEBUG**を定義することで、コンパイル時にアサーションチェックをオフにすることができます。 &lt;assert.h&gt; が組み込まれる前に `assert` コマンド ライン オプションを使用することにより、ソース ファイルを変更せずに **assert** マクロをオフにすることができます。 `assert` `#define NDEBUG` を含める前にディレクティブを使用して、ソースコードのマクロをオフにすることができ \<assert.h> ます。

`assert`*式*が (0) に評価され、が呼び出されてプログラムの実行が停止されると、マクロは診断メッセージを出力し **`false`** [`abort`](abort.md) ます。 *Expression*が **`true`** (0 以外) の場合、アクションは実行されません。 診断メッセージには、失敗した式、ソース ファイルの名前、アサーションが失敗した行番号が含まれます。

診断メッセージは、ワイド文字 () で出力され `wchar_t` ます。 そのため、式に Unicode 文字がある場合でも、予期したとおりに動作します。

ルーチンを呼び出したアプリケーションの種類に基づいて診断メッセージの出力先が決まります。 コンソールアプリケーションは、 **stderr**を通じてメッセージを受信します。 Windows ベースのアプリケーションでは、は、 `assert` Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) 関数を呼び出してメッセージボックスを作成し、3つのボタン ( **Abort**、 **Retry**、および **Ignore**) を使用してメッセージを表示します。 ユーザーが **[中止]** をクリックすると、プログラムはすぐに中止されます。 ユーザーが **[再試行]** をクリックすると、Just-In-Time (JIT) デバッグが有効になっている場合、デバッガーが呼び出され、ユーザーはプログラムをデバッグできます。 ユーザーが [ **無視**] をクリックすると、プログラムは通常の実行を続行します。 エラー状態が存在するときに [ **無視** ] をクリックすると、呼び出し元のコードの事前条件が満たされていないため、未定義の動作が発生する可能性があります。

アプリの種類に関係なく既定の出力動作をオーバーライドするには、を呼び出して、 [`_set_error_mode`](set-error-mode.md) stderr から stderr への出力と表示-ダイアログボックスの動作を選択します。

に `assert` よってメッセージが表示されると、が呼び出され [`abort`](abort.md) ます。このダイアログボックスには、[  **中止**]、[ **再試行**]、および [ **無視** ] ボタンが表示されます。 [`abort`](abort.md) プログラムを終了します。そのため、[ **再試行** ] と [ **無視** ] ボタンをクリックしても、呼び出し後のプログラムの実行は再開されません `assert` 。 `assert`ダイアログボックスが表示されている場合、 [`abort`](abort.md) ダイアログボックスは表示されません。 [`abort`](abort.md)ダイアログボックスが表示されるのは、が `assert` stderr に出力を送信するときだけです。

上記の動作の結果、デバッグモードでの呼び出しの後にダイアログボックスが常に表示され `assert` ます。 各ボタンの動作は次の表のようにキャプチャされます。

|エラーモード|Stderr への出力 (コンソール/_OUT_TO_STDERR)|[表示] ダイアログボックス (Windows/_OUT_TO_MSGBOX)|
|----------|----------------|------------------|
|中止|終了コード3を使用してすぐに終了する|終了コード3を使用してすぐに終了する|
|再試行|実行中にデバッガーを中断 `abort`|実行中にデバッガーを中断 `assert`|
|無視|終了の終了日 `abort`|Assert が起動されなかったかのようにプログラムを続行します (呼び出し元のコードの事前条件が満たされていないため、未定義の動作が発生する可能性があります)|

CRT デバッグの詳細については、「 [CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

`_assert` 関数と `_wassert` 関数は、内部 CRT 関数です。 これらは、アサーションをサポートするためのオブジェクト ファイルに必要なコードを最小限に抑えるうえで役立ちます。 これらの関数を直接呼び出すことはお勧めしません。

マクロは、 `assert` **NDEBUG** が定義されていない場合に、C ランタイムライブラリのリリースバージョンとデバッグバージョンの両方で有効になります。 **NDEBUG**が定義されている場合、マクロは使用できますが、引数は評価されず、効果はありません。 有効にすると、 `assert` マクロは `_wassert` その実装に対してを呼び出します。 その他のアサーション マクロの [_ASSERT](assert-asserte-assert-expr-macros.md)、[_ASSERTE](assert-asserte-assert-expr-macros.md)、[_ASSERT_EXPR](assert-asserte-assert-expr-macros.md) も使用できますが、これらは、[_DEBUG](../../c-runtime-library/debug.md) マクロが定義されており、かつ C ランタイム ライブラリのデバッグ バージョンとリンクされたコードにある場合にのみ、渡される式を評価します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`assert`, `_wassert`|\<assert.h>|

関数の署名は、 `_assert` ヘッダーファイルでは使用できません。 関数の署名 `_wassert` は、 **NDEBUG** マクロが定義されていない場合にのみ使用できます。

## <a name="example"></a>例

このプログラムでは、 **analyze_string** 関数はマクロを使用して、 `assert` 文字列と長さに関連するいくつかの条件をテストします。 条件のいずれかが失敗した場合、プログラムは失敗の原因を示すメッセージを出力します。

```C
// crt_assert.c
// compile by using: cl /W4 crt_assert.c
#include <stdio.h>
#include <assert.h>
#include <string.h>

void analyze_string( char *string );   // Prototype

int main( void )
{
   char  test1[] = "abc", *test2 = NULL, test3[] = "";

   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );
   analyze_string( test1 );
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );
   analyze_string( test2 );
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );
   analyze_string( test3 );
}

// Tests a string to see if it is NULL,
// empty, or longer than 0 characters.
void analyze_string( char * string )
{
   assert( string != NULL );        // Cannot be NULL
   assert( *string != '\0' );       // Cannot be empty
   assert( strlen( string ) > 2 );  // Length must exceed 2
}
```

プログラムは次の出力を生成します。

```Output
Analyzing string 'abc'
Analyzing string '(null)'
Assertion failed: string != NULL, file crt_assert.c, line 25
```

アサーションエラーが発生すると、オペレーティングシステムとランタイムライブラリのバージョンによっては、次のようなメッセージボックスが表示される場合があります。

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

デバッガーがインストールされている場合は **[デバッグ]** ボタンを選択してデバッガーを開始するか、 **[プログラムの終了]** をクリックして終了します。

## <a name="see-also"></a>関連項目

[エラー処理](../../c-runtime-library/error-handling-crt.md)<br/>
[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[取り消し](abort.md)<br/>
[発生](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
