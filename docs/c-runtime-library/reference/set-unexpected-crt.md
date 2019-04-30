---
title: set_unexpected (CRT)
ms.date: 11/04/2016
apiname:
- set_unexpected
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
apitype: DLLExport
f1_keywords:
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: 6c38421e447ca7b3f263148f51f0ade5c59e2804
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356400"
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

**unexpected** によって呼び出される独自の終了関数をインストールします。

## <a name="syntax"></a>構文

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>パラメーター

*されています*<br/>
置き換えるために作成する関数へのポインター、**予期しない**関数。

## <a name="return-value"></a>戻り値

によって登録された前の終了関数へのポインターを返し **_set_unexpected**前の関数を後で復元できるようにします。 戻り値を既定の動作を復元する使用可能性があります前の関数が設定されていない場合この値は、 **NULL**します。

## <a name="remarks"></a>Remarks

**Set_unexpected**インストールに機能*されています*によって呼び出される関数として**予期しない**します。 **予期しない**現在 C++ 例外処理の実装では使用されません。 **Unexpected_function**型 EH で定義されます。ユーザー定義の予期しない関数へのポインターとして H*されています*を返す**void**します。 カスタム*されています*関数が呼び出し元に返しません。

```cpp
typedef void ( *unexpected_function )( );
```

既定では、**予期しない**呼び出し**終了**します。 この既定の動作を変更するには、独自の終了関数を作成し、呼び出すことによって**set_unexpected**引数として関数の名前に置き換えます。 **予期しない**への引数として渡された最後関数を呼び出す**set_unexpected**します。

カスタムの終了関数への呼び出しによってインストールされているとは異なり**set_terminate**、内から例外をスローすることができます*されています*します。

マルチ スレッド環境では、予期しない関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの予期しない関数をインストールする必要があります。 したがって、各スレッドがそれぞれの予期しない処理を担当します。

C++ の例外処理の現在の Microsoft 実装で**予期しない**呼び出し**終了**既定し、例外処理の実行時のライブラリから呼び出されることはありません。 特定の利点を呼び出すことはありません**予期しない**なく**終了**します。

1 つは**set_unexpected**ハンドラーを動的にリンクされる Dll または Exe; を呼び出す場合でも**set_unexpected**ハンドラーが別のハンドラーに置き換え、またはによって設定されたハンドラーを交換します。別の DLL または exe ファイル。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**set_unexpected**|\<eh.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
