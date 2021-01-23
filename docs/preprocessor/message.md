---
description: pragmaMicrosoft C/c + + での message ディレクティブの詳細について説明します。
title: メッセージ pragma
ms.date: 01/22/2021
f1_keywords:
- message_CPP
- vc-pragma.message
helpviewer_keywords:
- message pragma
- pragma, message
no-loc:
- pragma
ms.openlocfilehash: 6f5e39896e0ba644f9d40665e80cbf7de9026223
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713494"
---
# <a name="message-no-locpragma"></a>`message` pragma

コンパイルを終了せずに、標準出力に文字列リテラルを送信します。

## <a name="syntax"></a>構文

> **`#pragma message(`***メッセージ-文字列***`)`**

## <a name="remarks"></a>解説

の一般的な使用方法 **`message`** pragma は、コンパイル時に情報メッセージを表示することです。

*メッセージ文字列* パラメーターには、文字列リテラルに展開されるマクロを使用できます。また、このようなマクロは、任意の組み合わせで文字列リテラルと連結できます。

で定義済みのマクロを使用する場合、 **`message`** pragma マクロは文字列を返す必要があります。 それ以外の場合は、マクロの出力を文字列に変換する必要があります。

次のコード片では、を使用して、 **`message`** pragma コンパイル中にメッセージを表示します。

```cpp
// pragma_directives_message1.cpp
// compile with: /LD
#if _M_IX86 >= 500
#pragma message("_M_IX86 >= 500")
#endif

#pragma message("")

#pragma message( "Compiling " __FILE__ )
#pragma message( "Last modified on " __TIMESTAMP__ )

#pragma message("")

// with line number
#define STRING2(x) #x
#define STRING(x) STRING2(x)

#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")

#pragma message("")
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
