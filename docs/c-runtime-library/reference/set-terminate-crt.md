---
title: set_terminate (CRT)
ms.date: 4/2/2020
api_name:
- set_terminate
- _o_set_terminate
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
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 70ed4adb7ceada53205fd69f111c8976fe95c711
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234017"
---
# <a name="set_terminate-crt"></a>set_terminate (CRT)

**Terminate**によって呼び出される独自の終了ルーチンをインストールします。

## <a name="syntax"></a>構文

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>パラメーター

*termFunction*<br/>
作成する終了関数へのポインター。

## <a name="return-value"></a>戻り値

前の関数を後で復元できるように、 **set_terminate**によって登録された前の関数へのポインターを返します。 前の関数が設定されていない場合は、戻り値を使用して既定の動作を復元できます。この値は**NULL**でもかまいません。

## <a name="remarks"></a>解説

**Set_terminate**関数は、**終了**によって呼び出される関数として*termfunction*をインストールします。 **set_terminate**は C++ 例外処理で使用され、例外がスローされる前にプログラムの任意の時点で呼び出すことができます。 **terminate**呼び出しは、既定で[中止](abort.md)されます。 独自の終了関数を記述し、関数の名前を引数として**set_terminate**を呼び出すことによって、この既定値を変更できます。 **terminate**は、 **set_terminate**の引数として渡された最後の関数を呼び出します。 必要なクリーンアップタスクを実行した後、 *Termfunction*はプログラムを終了する必要があります。 終了しない場合 (呼び出し元に戻る場合)、 [abort](abort.md)が呼び出されます。

マルチ スレッド環境では、終了関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの終了関数をインストールする必要があります。 したがって、各スレッドがそれぞれの終了処理を担当します。

**Terminate_function**型は EH で定義されています。ユーザー定義の終了関数へのポインターとしての H、を返す*termfunction* **`void`** 。 カスタム関数*Termfunction*は引数を取らず、呼び出し元に戻らないようにする必要があります。 この場合、 [abort](abort.md)が呼び出されます。 *Termfunction*内から例外がスローされない可能性があります。

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate**関数は、デバッガーの外部でのみ機能します。

動的にリンクされたすべての Dll または Exe に対して1つの**set_terminate**ハンドラーがあります。を呼び出した場合でも、ハンドラーを別の DLL または別の DLL または EXE によって設定されたハンドラーに置き換えることが**set_terminate**ます。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[terminate](terminate-crt.md) の例をご覧ください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[を呼び出してプログラム実行を終了する際、](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[解約](terminate-crt.md)<br/>
[不適切](unexpected-crt.md)<br/>
