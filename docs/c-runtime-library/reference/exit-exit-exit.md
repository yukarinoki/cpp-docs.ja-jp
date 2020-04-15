---
title: 終了、_Exit、_exit
ms.date: 4/2/2020
api_name:
- _exit
- exit
- _o__exit
- _o_exit
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.openlocfilehash: 5bdb5ff5c8309e03a49f9518f65a45d5757e9bfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347634"
---
# <a name="exit-_exit-_exit"></a>終了、_Exit、_exit

呼び出しプロセスを終了します。 **終了**関数は、クリーンアップ後に終了します。**_exit**し、**すぐに終了_Exit。**

> [!NOTE]
> テストまたはデバッグのシナリオを除き、ユニバーサル Windows プラットフォーム (UWP) アプリをシャットダウンするには、このメソッドを使用しないでください。 ストア アプリを閉じるプログラムまたは UI の方法は、 [Microsoft Store のポリシー](/legal/windows/agreements/store-policies)に従って許可されていません。 詳細については[、「UWP アプリのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)」を参照してください。 Windows 10 アプリについて詳しくは、「 [Windows 10 アプリの使用方法のガイド](https://developer.microsoft.com/windows/apps)」をご覧ください。

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

*status*<br/>
終了ステータス コード。

## <a name="remarks"></a>解説

**exit** **、_Exit、****および_exit**関数は、呼び出しプロセスを終了します。 **exit**関数はスレッド ローカル オブジェクトのデストラクターを呼び出し **、atexit**と **_onexit**によって登録された関数を呼び出し、その後、プロセスを終了する前にすべてのファイル バッファをフラッシュします。 **_Exit**関数と **_exit**関数は、スレッドローカルオブジェクトを破棄したり **、atexit**または **_onexit**関数を処理したり、ストリームバッファをフラッシュしたりすることなく、プロセスを終了します。

**exit、_Exit、****exit****および_exit**呼び出しは値を返しませんが、プロセスの終了後に *、状態*の値はホスト環境または待機呼び出しプロセス (存在する場合) に使用可能になります。 通常、呼び出し元は、通常の終了を示すには、またはエラーを示す他の値に *、状況*値を 0 に設定します。 オペレーティング システム バッチ コマンド**ERRORLEVEL**で*状態*値を使用でき、値 0 を表す**EXIT_SUCCESS、** または値 1 を表す**EXIT_FAILURE**の 2 つの定数のいずれかによって表されます。

**exit**、 **_Exit**、 **_exit**、 **quick_exit**、 **_cexit**、および **_c_exit**関数は、次のように動作します。

|機能|説明|
|--------------|-----------------|
|**終了**|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_exit**|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_exit**|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**quick_exit**|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_cexit**|完全な C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|
|**_c_exit**|最低限の C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|

**exit**関数 **、_Exit**関数、または **_exit**関数を呼び出すとき、呼び出し時に存在する一時オブジェクトまたは自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトは、関数で定義された非静的ローカルオブジェクトです。 一時オブジェクトは、関数呼び出しによって返される値など、コンパイラによって作成されるオブジェクトです。 **exit、** **_Exit**、または **_exit**を呼び出す前に自動オブジェクトを破棄するには、次のようにオブジェクトのデストラクターを明示的に呼び出します。

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

**dllMain**から**終了**を呼び出すために**DLL_PROCESS_ATTACH**を使用しないでください。 **DLLMain**関数を終了するには **、DLL_PROCESS_ATTACH**から**FALSE**を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**終了**, **_Exit**, **_exit**|\<process.h> または \<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[中止](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit、_c_exit](cexit-c-exit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
