---
title: setlocale プラグマ
ms.date: 08/29/2019
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
ms.openlocfilehash: 9603c132610e0cfb1e8f955be48271870527105b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219379"
---
# <a name="setlocale-pragma"></a>setlocale プラグマ

ワイド文字定数とリテラル文字列を変換するときに使用する*ロケール*、国、地域、および言語を定義します。

## <a name="syntax"></a>構文

> **#pragma setlocale ("** [ *locale-string* ] **")**

## <a name="remarks"></a>解説

マルチバイト文字をワイド文字に変換するためのアルゴリズムはロケールによって異なる場合があります。また、コンパイルは実行可能ファイルを実行する別のロケールで実行される可能性があるため、このプラグマを使用すると、コンパイル時にターゲットロケールを指定することができます。 これは、ワイド文字列が正しい形式で格納されることを保証します。

既定の*ロケール文字列*は "" です。

"C" ロケールは、文字列内の各文字をとして値にマップし **`wchar_t`** ます。 のその他の有効な値 `setlocale` は、[[言語文字列](../c-runtime-library/language-strings.md)] ボックスの一覧にあるエントリです。 たとえば、次のように指定できます。

```cpp
#pragma setlocale("dutch")
```

言語文字列を指定する機能は、お使いのコンピューターのコードページと言語 ID のサポートによって異なります。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
