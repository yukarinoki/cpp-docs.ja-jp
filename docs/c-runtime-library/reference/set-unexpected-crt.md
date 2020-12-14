---
description: 詳細については、「set_unexpected (CRT)」を参照してください。
title: set_unexpected (CRT)
ms.date: 11/04/2016
api_name:
- set_unexpected
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: b9665a73f87d64cd991ff8ce296a4c14957b30ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211077"
---
# <a name="set_unexpected-crt"></a>set_unexpected (CRT)

**unexpected** によって呼び出される独自の終了関数をインストールします。

## <a name="syntax"></a>構文

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>パラメーター

*Un関数*<br/>
**予期しない** 関数を置き換えるために記述する関数へのポインター。

## <a name="return-value"></a>戻り値

前の関数を後で復元できるように、 **_set_unexpected** によって登録された前の終了関数へのポインターを返します。 前の関数が設定されていない場合は、戻り値を使用して既定の動作を復元できます。この値は **NULL** でもかまいません。

## <a name="remarks"></a>解説

**Set_unexpected** 関数は、**予期しない** によって呼び出された関数として *関数* をインストールします。 現在の C++ 例外処理の実装では、**予期** しないが使用されています。 **Unexpected_function** 型は EH で定義されています。ユーザー定義の予期しない関数へのポインターとしての H。を返す *関数* **`void`** 。 *カスタム関数関数は*、呼び出し元に戻らないようにする必要があります。

```cpp
typedef void ( *unexpected_function )( );
```

既定では、 **予期しない** 呼び出しは **終了** します。 この既定の動作を変更するには、独自の終了関数を記述し、関数の名前を引数として **set_unexpected** を呼び出します。 **予期しない** 呼び出し **set_unexpected** の引数として渡された最後の関数。

**Set_terminate** の呼び出しによってインストールされるカスタムの終了関数とは異なり、*関数* 内から例外をスローできます。

マルチ スレッド環境では、予期しない関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの予期しない関数をインストールする必要があります。 したがって、各スレッドがそれぞれの予期しない処理を担当します。

現在の C++ 例外処理の実装では、 **予期しない** 呼び出しが既定で **終了** し、例外処理ランタイムライブラリによって呼び出されることはありません。 **終了** するのではなく、**予期しない** 呼び出しを行う利点はありません。

動的にリンクされたすべての Dll または Exe に対して1つの **set_unexpected** ハンドラーがあります。を呼び出した場合でも、ハンドラーを別の DLL または別の DLL または EXE によって設定されたハンドラーに置き換えることが **set_unexpected** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**set_unexpected**|\<eh.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[取り消し](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[解約](terminate-crt.md)<br/>
[不適切](unexpected-crt.md)<br/>
