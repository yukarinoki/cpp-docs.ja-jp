---
title: exit、_Exit、_exit | Microsoft ドキュメント
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb62c18f7508a21e24fb5628e8ac01162db1405e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="exit-exit-exit"></a>終了、_Exit、_exit

呼び出しプロセスを終了します。 **終了**関数はクリーンアップ後に終了 **_exit**と **_Exit**直ちに終了します。

> [!NOTE]
> このメソッドを使用して、テスト シナリオまたはデバッグ シナリオにを除き、ユニバーサル Windows プラットフォーム (UWP) アプリをシャット ダウンしないでください。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](/legal/windows/agreements/store-policies)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)です。 Windows 10 アプリについて詳しくは、「 [Windows 10 アプリの使用方法のガイド](http://go.microsoft.com/fwlink/p/?linkid=619133)」をご覧ください。

## <a name="syntax"></a>構文

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit(
   int const status
);
```

### <a name="parameters"></a>パラメーター

*ステータス*状態コードを終了します。

## <a name="remarks"></a>コメント

**終了**、 **_Exit**と **_exit**関数が呼び出し元のプロセスを終了します。 **終了**関数がデストラクターを呼び出すスレッド ローカル オブジェクトの呼び出し、— 最後先出し (LIFO) の順序で — によって登録されている関数**atexit**と **_onexit**、し、プロセスが終了する前にすべてのファイル バッファーをフラッシュします。 **_Exit**と **_exit**関数は、スレッド ローカル オブジェクトの破棄または処理せず、プロセスを終了**atexit**または **_onexit**関数、およびストリーム バッファーのフラッシュします。

**終了**、 **_Exit**と **_exit**呼び出しは、値の値を返しません*ステータス*ホスト環境に使用可能になりますまたは、いずれかが存在する場合、プロセスの終了後に呼び出し元のプロセスを待機しています。 呼び出し元のセットでは通常、*ステータス*値を 0 に通常の終了を示すため、または他のエラーを示す値。 *ステータス*値は、オペレーティング システムのバッチ コマンドを使用可能な**ERRORLEVEL** 、2 つの定数のいずれかで表されます**EXIT_SUCCESS**、値を表す。0、または**EXIT_FAILURE**1 の値を表します。

**終了**、 **_Exit**、 **_exit**、 **quick_exit**、 **_cexit**、および **_c_exit**関数の次のように動作します。

|関数|説明|
|--------------|-----------------|
|**exit**|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_Exit**|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_exit**|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**quick_exit**|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_cexit**|完全な C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|
|**_c_exit**|最低限の C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|

呼び出すと、**終了**、 **_Exit**または **_exit**関数の呼び出し時に存在する一時または自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトは、関数で定義されている非静的ローカル オブジェクトです。 一時オブジェクトは、関数呼び出しによって返される値など、コンパイラによって作成されるオブジェクトです。 呼び出す前に自動オブジェクトを破棄する**終了**、 **_Exit**、または **_exit**、明示的に次のように、オブジェクトのデストラクターを呼び出します。

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

使用しないでください**DLL_PROCESS_ATTACH**を呼び出す**終了**から**DllMain**です。 終了する、 **DLLMain**関数を返す**FALSE**から**DLL_PROCESS_ATTACH**です。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**終了**、 **_Exit**、 **_exit**|\<process.h> または \<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit、_c_exit](cexit-c-exit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
