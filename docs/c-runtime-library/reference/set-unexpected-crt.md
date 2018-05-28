---
title: set_unexpected (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7af5cce0b17747beb8c136f75489025d741f864a
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

**unexpected** によって呼び出される独自の終了関数をインストールします。

## <a name="syntax"></a>構文

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>パラメーター

*されています*<br/>
置換するために作成関数へのポインター、**予期しない**関数。

## <a name="return-value"></a>戻り値

によって登録されている以前の終了関数へのポインターを返します **_set_unexpected**前の関数を後で復元できるようにします。 戻り値を既定の動作を復元する使用可能性がありますの前の関数が設定されていない場合この値は、 **NULL**です。

## <a name="remarks"></a>コメント

**Set_unexpected**インストールに機能*されています*によって呼び出される関数として**予期しない**です。 **予期しない**現在 C++ 例外処理の実装では使用されません。 **Unexpected_function**型 EH で定義されます。ユーザー定義の予期しない関数へのポインターとして H*されています*を返す**void**です。 カスタム*されています*関数は、呼び出し元に返されません。

```cpp
typedef void ( *unexpected_function )( );
```

既定では、**予期しない**呼び出し**終了**です。 この既定の動作を変更するには、独自の終了関数を記述して呼び出すこと**set_unexpected**関数の引数としての名前に置き換えます。 **予期しない**に渡す引数として指定されている最後の関数を呼び出す**set_unexpected**です。

呼び出しによってインストールされているカスタムの終了関数とは異なり**set_terminate**、内から例外をスローできる*されています*です。

マルチ スレッド環境では、予期しない関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの予期しない関数をインストールする必要があります。 したがって、各スレッドがそれぞれの予期しない処理を担当します。

C++ 例外処理の現在の Microsoft 実装で**予期しない**呼び出し**終了**既定と例外処理のランタイム ライブラリによって呼び出されることはありません。 特定の利点を呼び出すことはありません**予期しない**なく**終了**です。

1 つ**set_unexpected**のハンドラーを動的にリンクされる Dll または Exe; を呼び出す場合でも**set_unexpected**ハンドラーが別のハンドラーに置き換え、またはによって設定されたハンドラーを交換します。別の DLL または EXE です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
