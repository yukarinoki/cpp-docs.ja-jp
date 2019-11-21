---
title: ソフトウェア例外の発生
ms.date: 11/04/2016
helpviewer_keywords:
- run-time errors, treating as exceptions
- exception handling [C++], errors as exceptions
- exceptions [C++], flagging errors as exceptions
- errors [C++], treating as exceptions
- exception handling [C++], detecting errors
- structured exception handling [C++], errors as exceptions
- exceptions [C++], software
- RaiseException function
- software exceptions [C++]
- formats [C++], exception codes
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
ms.openlocfilehash: 7c58ae2e2b6635345a162d11d2b75a9865d37751
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246406"
---
# <a name="raising-software-exceptions"></a>ソフトウェア例外の発生

プログラム エラーの最も一般的な原因のいくつかは、システムによって例外としてフラグが設定されません。 たとえば、メモリ ブロックを割り当てるときにメモリが不足していると、ランタイム関数または API 関数で例外は発生しませんが、エラー コードが返されます。

However, you can treat any condition as an exception by detecting that condition in your code and then reporting it by calling the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function. この方法でエラーにフラグを設定すれば、構造化例外処理の長所をあらゆるランタイム エラーに取り込むことができます。

エラーで構造化例外処理を使用するには、次の手順に従います。

- イベントごとに例外コードを定義します。

- Call `RaiseException` when you detect a problem.

- 例外処理フィルターを使用して、定義した例外コードをテストします。

The \<winerror.h> file shows the format for exception codes. 既存の例外コードと競合するコードを定義しないように、第 3 上位ビットを 1 に設定します。 4 つの最上位ビットは、次の表に示すように設定する必要があります。

|Bits|推奨バイナリ設定|説明|
|----------|--------------------------------|-----------------|
|31-30|11|これら 2 つのビットは、コードの基本的なステータスを示します (11 = エラー、00 = 成功、01 = 情報、10 = 警告)。|
|29|1|クライアント ビット。 ユーザー定義コードの場合は 1 に設定します。|
|28|0|予約済みのビット (0 に設定しておきます)。|

必要であれば、最初の 2 ビットをバイナリ 11 以外に設定できますが、通常はほとんどの例外に "エラー" を設定します。 注意すべき重要事項は、前の表に示すようにビット 29 と 28 を設定することです。

The resulting error code should therefore have the highest four bits set to hexadecimal E. For example, the following definitions define exception codes that do not conflict with any Windows exception codes. (ただし、サード パーティの DLL がどのコードを使用するか確認する必要があります)。

```cpp
#define STATUS_INSUFFICIENT_MEM       0xE0000001
#define STATUS_FILE_BAD_FORMAT        0xE0000002
```

例外コードを定義したら、そのコードを使用して例外を発生させることができます。 For example, the following code raises the `STATUS_INSUFFICIENT_MEM` exception in response to a memory allocation problem:

```cpp
lpstr = _malloc( nBufferSize );
if (lpstr == NULL)
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);
```

例外を簡単に発生させるには、最後の 3 つのパラメーターを 0 に設定します。 最後の 3 つのパラメーターは、追加情報を渡し、ハンドラーの実行を中止するフラグを設定するときに使用します。 See the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function in the Windows SDK for more information.

例外処理フィルターで、定義したコードをテストできます。 (例:

```cpp
__try {
    ...
}
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )
```

## <a name="see-also"></a>関連項目

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[Structured exception handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)