---
title: assert マクロ、_assert、_wassert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- assert
- _assert
- _wassert
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0318abde877e9b647c1781408d2e22cc9d70824e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397842"
---
# <a name="assert-macro-assert-wassert"></a>assert マクロ、_assert、_wassert

式を評価、結果が**false**、診断メッセージを表示し、プログラムを中止します。

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

*式*0 以外に評価されるスカラー式 (ポインター式を含む) (**true**) または 0 (**false**)。

*メッセージ*表示するメッセージ。

*filename*ファイルに失敗したアサーションのソースの名前。

*行*失敗したアサーションのソース ファイル内の行番号。

## <a name="remarks"></a>コメント

**アサート**マクロは、通常、プログラムの開発中に論理エラーを識別に使用します。 予期しない条件が実装することによって発生したときに、プログラムの実行を停止して、*式*に評価される引数**false**のみと、プログラムが正しく動作しません。 アサーション チェックを無効にできますコンパイル時にマクロを定義することによって**NDEBUG**です。 オフにすることができます、**アサート**マクロを使用して、ソース ファイルを変更することがなく、 **/DNDEBUG**コマンド ライン オプションです。 オフにすることができます、**アサート**マクロを使用して、ソース コードで、`#define NDEBUG`ディレクティブを\<assert.h > が含まれる。

**アサート**診断メッセージ マクロ印刷*式*に評価される**false** (0) と呼び出し[中止](abort.md)プログラムを終了するには実行します。 場合アクションは実行されません*式*は**true** (0 以外)。 診断メッセージには、失敗した式、ソース ファイルの名前、アサーションが失敗した行番号が含まれます。

診断メッセージはワイド文字で出力されます。 したがって、式に Unicode 文字がある場合でも、予期していたとおりに機能します。

ルーチンを呼び出したアプリケーションの種類に基づいて診断メッセージの出力先が決まります。 コンソール アプリケーションは常に使用してメッセージを受信**stderr**です。 Windows ベースのアプリケーションで**アサート**、Windows を呼び出して[メッセージ ボックス](http://msdn.microsoft.com/library/windows/desktop/ms645505)と共にメッセージを表示するメッセージ ボックスを作成する関数、 **[ok]** ボタンをクリックします。 ユーザーが **[OK]** をクリックすると、プログラムはすぐに中止されます。

アプリケーションがランタイム ライブラリのデバッグ バージョンとリンクされている場合**アサート**3 つのボタンでメッセージ ボックスを作成:**中止**、**再試行**、および**無視**です。 ユーザーが **[中止]** をクリックすると、プログラムはすぐに中止されます。 ユーザーが **[再試行]** をクリックすると、Just-In-Time (JIT) デバッグが有効になっている場合、デバッガーが呼び出され、ユーザーはプログラムをデバッグできます。 ユーザーがクリックした場合**無視**、**アサート**、通常の実行を続行: を含むメッセージ ボックスを作成する、 **[ok]** ボタンをクリックします。 なお、エラー状況が存在するときに **[無視]** をクリックすると、"未定義の動作" という結果になることがあります。

CRT デバッグの詳細については、「 [CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

**_Assert**と **_wassert**関数は、内部 CRT 関数。 これらは、アサーションをサポートするためのオブジェクト ファイルに必要なコードを最小限に抑えるうえで役立ちます。 これらの関数を直接呼び出すことはお勧めしません。

**アサート**マクロが C ランタイム ライブラリのリリース バージョンとデバッグ バージョンの両方で有効にしたときに**NDEBUG**が定義されていません。 ときに**NDEBUG**が定義されている場合、マクロは使用可能なですが、引数を評価せずとも何も起こりません。 有効になっているときに、**アサート**マクロの呼び出し **_wassert**のため、実装します。 その他のアサーション マクロの [_ASSERT](assert-asserte-assert-expr-macros.md)、[_ASSERTE](assert-asserte-assert-expr-macros.md)、[_ASSERT_EXPR](assert-asserte-assert-expr-macros.md) も使用できますが、これらは、[_DEBUG](../../c-runtime-library/debug.md) マクロが定義されており、かつ C ランタイム ライブラリのデバッグ バージョンとリンクされたコードにある場合にのみ、渡される式を評価します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**アサート**、 **_wassert**|\<assert.h>|

署名、 **_assert**関数には、ヘッダー ファイルでは使用できません。 署名、 **_wassert**関数は、のみ使用可能な場合に、 **NDEBUG**マクロが定義されていません。

## <a name="example"></a>例

このプログラムで、 **analyze_string**関数は、**アサート**文字列と長さに関連するいくつかの条件をテストするマクロです。 条件のいずれかが失敗した場合、プログラムは失敗の原因を示すメッセージを出力します。

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

アサーションが失敗した後、オペレーティング システムとランタイム ライブラリのバージョンに応じて、以下のような内容のメッセージ ボックスが表示される可能性があります。

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

デバッガーがインストールされている場合は **[デバッグ]** ボタンを選択してデバッガーを開始するか、 **[プログラムの終了]** をクリックして終了します。

## <a name="see-also"></a>関連項目

[エラー処理](../../c-runtime-library/error-handling-crt.md)<br/>
[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT、_ASSERTE、_ASSERT_EXPR Macros](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
