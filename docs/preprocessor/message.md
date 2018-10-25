---
title: メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs:
- C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98cdb6e089b972bbc53a6816287595d952aed1f5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083543"
---
# <a name="message"></a>message
コンパイルを終了せずに、標準出力に文字列リテラルを送信します。

## <a name="syntax"></a>構文

```
#pragma message( messagestring )
```

## <a name="remarks"></a>Remarks

一般的な使用、**メッセージ**プラグマは、コンパイル時に情報メッセージを表示します。

*Messagestring*パラメーターは、リテラル文字列に展開されるマクロは、こうしたマクロと文字列リテラルの任意の組み合わせを連結することができます。

定義済みマクロを使用する場合、**メッセージ**プラグマ マクロが文字列を返す必要があります、それ以外の場合、マクロの出力を文字列に変換する必要があります。

次のコード フラグメントを使用して、**メッセージ**プラグマはコンパイル時にメッセージを表示します。

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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)