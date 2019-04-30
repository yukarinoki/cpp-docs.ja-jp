---
title: set_terminate (CRT)
ms.date: 11/04/2016
apiname:
- set_terminate
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
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 7be81dec7fba80a273d635cbd30b96b09928bc66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356447"
---
# <a name="setterminate-crt"></a>set_terminate (CRT)

によって呼び出される独自の終了ルーチンをインストール**終了**します。

## <a name="syntax"></a>構文

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>パラメーター

*termFunction*<br/>
作成する終了関数へのポインター。

## <a name="return-value"></a>戻り値

によって登録された前の関数へのポインターを返します**set_terminate**前の関数を後で復元できるようにします。 戻り値を既定の動作を復元する使用可能性があります前の関数が設定されていない場合この値は、 **NULL**します。

## <a name="remarks"></a>Remarks

**Set_terminate**インストールに機能*termFunction*によって呼び出される関数として**終了**します。 **set_terminate**併用C++例外処理と、例外がスローされる前に、プログラムのどの時点でも呼び出すことができます。 **終了**呼び出し[中止](abort.md)既定。 この既定の設定を変更するには、独自の終了関数を作成し、呼び出すことによって**set_terminate**引数として関数の名前に置き換えます。 **終了**への引数として渡された最後関数を呼び出す**set_terminate**します。 必要なクリーンアップ タスクのいずれかを実行した後*termFunction*プログラムを終了する必要があります。 かどうか (この場合、呼び出し元に返す) 終了せず、[中止](abort.md)が呼び出されます。

マルチ スレッド環境では、終了関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの終了関数をインストールする必要があります。 したがって、各スレッドがそれぞれの終了処理を担当します。

**Terminate_function**型 EH で定義されます。ユーザー定義の終了関数へのポインターとして H *termFunction*を返す**void**します。 カスタム関数*termFunction*できます引数を受け取らず、呼び出し元には返されません。 その場合、[中止](abort.md)が呼び出されます。 内から例外をスローしない可能性が*termFunction*します。

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate**関数は、デバッガーの外部でのみ機能します。

1 つは**set_terminate**ハンドラーを動的にリンクされる Dll または Exe; を呼び出す場合でも**set_terminate**を他のハンドラーを置き換えることができますか、別によって設定されたハンドラーを置き換えることがありますDLL または exe ファイル。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[terminate](terminate-crt.md) の例をご覧ください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
