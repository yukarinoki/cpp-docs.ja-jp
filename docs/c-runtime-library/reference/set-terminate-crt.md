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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 08ea5bb8c446fadac6a7bcf7ca172c5d14546776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332101"
---
# <a name="set_terminate-crt"></a>set_terminate (CRT)

**terminate**によって呼び出される独自の終了ルーチンをインストールします。

## <a name="syntax"></a>構文

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>パラメーター

*関数*<br/>
作成する終了関数へのポインター。

## <a name="return-value"></a>戻り値

前の関数を後で復元できるように **、set_terminate**によって登録された以前の関数へのポインターを返します。 以前の関数が設定されていない場合は、戻り値を使用して既定の動作を復元できます。この値は**NULL の**場合があります。

## <a name="remarks"></a>解説

**set_terminate**関数は **、terminate**によって呼び出される関数として*termFunction*をインストールします。 **set_terminate**は C++ 例外処理で使用され、例外がスローされる前にプログラム内の任意の時点で呼び出すことができます。 **終了**呼び出しはデフォルトで[中止](abort.md)されます。 このデフォルトは、独自の終了関数を記述し、関数の名前を引数として**set_terminate**呼び出すことで変更できます。 **terminate**は **、set_terminate**の引数として指定された最後の関数を呼び出します。 必要なクリーンアップ タスクを実行した後 *、termFunction*はプログラムを終了する必要があります。 終了しない場合 (呼び出し元に戻る場合[)、abort](abort.md)が呼び出されます。

マルチ スレッド環境では、終了関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの終了関数をインストールする必要があります。 したがって、各スレッドがそれぞれの終了処理を担当します。

**terminate_function**タイプは EH で定義されます。H はユーザー定義の終了関数へのポインターとして、 **void**を返す*termFunction*です。 カスタム関数*termFunction*は引数を受け取らず、呼び出し元に戻るべきではありません。 その場合は[、abort](abort.md)が呼び出されます。 例外は *、関数の中*からスローすることはできません。

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **set_terminate**関数は、デバッガー以外でのみ機能します。

動的にリンクされるすべての DLL または EXE に対して **、1**つの set_terminate ハンドラーがあります。ハンドラーを呼び出**set_terminate**別のハンドラーに置き換えられたり、別の DLL または EXE によって設定されたハンドラーを置き換えたりする場合でも、この方法を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[terminate](terminate-crt.md) の例をご覧ください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[中止](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[終了](terminate-crt.md)<br/>
[予期 しない](unexpected-crt.md)<br/>
