---
description: pragmaMicrosoft C/c + + での setlocale ディレクティブの詳細について説明します。
title: setlocale pragma
ms.date: 01/22/2021
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragma, setlocale
- setlocale pragma
no-loc:
- pragma
ms.openlocfilehash: 936aa1c2eb26798438b48e61ec28007a12080f28
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713208"
---
# <a name="setlocale-no-locpragma"></a>`setlocale` pragma

ワイド文字定数とリテラル文字列を変換するときに使用する *ロケール*、国、地域、および言語を定義します。

## <a name="syntax"></a>構文

> **`#pragma setlocale( "`** [ *ロケール文字列* ] **`" )`**

## <a name="remarks"></a>解説

マルチバイト文字をワイド文字に変換するためのアルゴリズムはロケールによって異なる場合があります。また、コンパイルは実行可能ファイルが実行される別のロケールで実行される可能性があるため、 pragma コンパイル時にターゲットロケールを指定する方法が用意されています。 これは、ワイド文字列が正しい形式で格納されることを保証します。

既定の *ロケール文字列* は、によって指定された空の文字列です `#pragma setlocale( "" )` 。

ロケールは、 **`"C"`** 文字列内の各文字をとして値にマップし **`wchar_t`** ます。 のその他の有効な値 `setlocale` は、[ [言語文字列](../c-runtime-library/language-strings.md) ] ボックスの一覧にあるエントリです。 たとえば、次のように指定できます。

```cpp
#pragma setlocale("dutch")
```

言語文字列を指定する機能は、お使いのコンピューターのコードページと言語 ID のサポートによって異なります。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
