---
title: set_terminate (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e62dc1e4f99a1d2707c6e7b86c79e0ffc8aa027
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450977"
---
# <a name="setterminate-crt"></a>set_terminate (CRT)

によって呼び出される独自の終了ルーチンをインストール**終了**です。

## <a name="syntax"></a>構文

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>パラメーター

*termFunction*<br/>
作成する終了関数へのポインター。

## <a name="return-value"></a>戻り値

によって登録前の関数のポインターを返します**set_terminate**前の関数を後で復元できるようにします。 戻り値を既定の動作を復元する使用可能性がありますの前の関数が設定されていない場合この値は、 **NULL**です。

## <a name="remarks"></a>コメント

**Set_terminate**インストールに機能*termFunction*によって呼び出される関数として**終了**です。 **set_terminate** C++ 例外処理で使用され、例外がスローされる前に、プログラムのどの時点でも呼び出すことができます。 **終了**呼び出し[中止](abort.md)既定です。 この既定の設定を変更するには、独自の終了関数を記述して呼び出すこと**set_terminate**関数の引数としての名前に置き換えます。 **終了**に渡す引数として指定されている最後の関数を呼び出す**set_terminate**です。 必要なクリーンアップ タスクのいずれかを実行した後*termFunction*プログラムを終了する必要があります。 かどうかに終了しない場合、呼び出し元に返します)、[中止](abort.md)と呼びます。

マルチ スレッド環境では、終了関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの終了関数をインストールする必要があります。 したがって、各スレッドがそれぞれの終了処理を担当します。

**Terminate_function**型 EH で定義されます。終了のユーザー定義関数へのポインターとして H *termFunction*を返す**void**です。 ユーザー定義関数*termFunction*できる引数を取らず、呼び出し元には返されません。 その場合、[中止](abort.md)と呼びます。 内から、例外がスローされない場合があります*termFunction*です。

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate**機能は、デバッガーの外部でのみ機能します。

1 つ**set_terminate**のハンドラーを動的にリンクされる Dll または Exe; を呼び出す場合でも**set_terminate**を他のハンドラーを置き換えることができますか、別で設定されたハンドラーを置き換えることがありますDLL または EXE です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
