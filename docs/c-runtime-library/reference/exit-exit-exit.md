---
description: 詳細については、「exit、_Exit、_exit」を参照してください。
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b2d5a95f8a110e467016be828418050d77caa984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236036"
---
# <a name="exit-_exit-_exit"></a>終了、_Exit、_exit

呼び出しプロセスを終了します。 **Exit** 関数は、クリーンアップ後に終了します。**_exit** 、 **_Exit** 直ちに終了します。

> [!NOTE]
> テストシナリオまたはデバッグシナリオを除き、このメソッドを使用してユニバーサル Windows プラットフォーム (UWP) アプリをシャットダウンしないでください。 プログラムまたは UI がストアアプリを閉じる方法は、 [Microsoft Store ポリシー](/legal/windows/agreements/store-policies)によっては許可されていません。 詳細については、「 [UWP アプリのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)」を参照してください。 Windows 10 アプリについて詳しくは、「 [Windows 10 アプリの使用方法のガイド](https://developer.microsoft.com/windows/apps)」をご覧ください。

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

**Exit**、 **_Exit** 、 **_exit** の各関数は、呼び出し元のプロセスを終了します。 **Exit** 関数は、スレッドローカルオブジェクトのデストラクターを呼び出し、次に、 **atexit** および **_onexit** によって登録された関数を後入れ先出し (LIFO) の順序で呼び出し、プロセスを終了する前にすべてのファイルバッファーをフラッシュします。 **_Exit** 関数と **_exit** 関数は、スレッドローカルオブジェクトを破棄せずにプロセスを終了します。また、 **atexit** または **_onexit** 関数を処理したり、ストリームバッファーをフラッシュしたりすることはありません。

**終了**、 **_Exit** および **_exit** 呼び出しは値を返しませんが、プロセスが終了した後、ホスト環境で [*状態*] の値を使用できるようになります (存在する場合)。 通常、呼び出し元は *状態* 値を0に設定して、通常の終了を示すか、またはエラーを示す他の値に設定します。 *Status* 値は、オペレーティングシステムのバッチコマンド **ERRORLEVEL** で使用でき、値0を表す **EXIT_SUCCESS**、または値1を表す **EXIT_FAILURE** の2つの定数のいずれかによって表されます。

**Exit**、 **_Exit**、 **_exit**、 **quick_exit**、 **_cexit**、および **_c_exit** の各関数は、次のように動作します。

|機能|説明|
|--------------|-----------------|
|**exit**|完全な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_Exit**|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_exit**|最低限の C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**quick_exit**|高速な C ライブラリの終了処理を実行してプロセスを終了し、指定されたステータス コードをホスト環境に提供します。|
|**_cexit**|完全な C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|
|**_c_exit**|最低限の C ライブラリの終了処理を実行し、呼び出し元に戻ります。 プロセスを終了しません。|

**Exit**、 **_Exit** または **_exit** 関数を呼び出すと、呼び出し時に存在する一時オブジェクトまたは自動オブジェクトのデストラクターは呼び出されません。 自動オブジェクトは、関数で定義された非静的ローカルオブジェクトです。 一時オブジェクトは、関数呼び出しによって返される値など、コンパイラによって作成されるオブジェクトです。 **Exit**、 **_Exit**、または **_exit** を呼び出す前に自動オブジェクトを破棄するには、次に示すように、オブジェクトのデストラクターを明示的に呼び出します。

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

**DLL_PROCESS_ATTACH** を使用して、 **DllMain** から **exit** を呼び出さないでください。 **DLLMain** 関数を終了するには、 **DLL_PROCESS_ATTACH** から **FALSE** を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|機能|必須ヘッダー|
|--------------|---------------------|
|**exit**、 **_Exit**、 **_exit**|\<process.h> または \<stdlib.h>|

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
[取り消し](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit、_c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec 関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn, _wspawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
