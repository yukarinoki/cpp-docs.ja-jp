---
title: コンパイラの警告 (レベル 1) C4067 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4067
dev_langs:
- C++
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee6b48327e8754f9388e0df8f43009a5be70c97
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-warning-level-1-c4067"></a>コンパイラの警告 (レベル 1) C4067

> 予期しないトークン プリプロセッサ ディレクティブの後に改行が必要です

## <a name="remarks"></a>コメント

コンパイラが見つかりプリプロセッサ ディレクティブに続く余分な文字を無視します。 可能性があります、任意の予期しない文字では一般的な原因は無効なセミコロン ディレクティブの後です。 コメントでは、この警告は発生しません。 **/Za**コンパイラ オプションの既定の設定よりも詳細のプリプロセッサ ディレクティブには、この警告を有効にします。

## <a name="example"></a>例

```cpp
// C4067a.cpp
// compile with: cl /EHsc /DX /W1 /Za C4067a.cpp
#include <iostream>
#include <string> s     // C4067
#if defined(X);         // C4067
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif;                 // C4067 only under /Za
int main()
{
    std::cout << s << std::endl;
}
```

この警告を解決するのには、無効な文字を削除またはコメント ブロック内に移動します。 削除することで、特定 C4067 警告を無効にすることがあります、 **/Za**コンパイラ オプション。

```cpp
// C4067b.cpp
// compile with: cl /EHsc /DX /W1 C4067b.cpp
#include <iostream>
#include <string>
#if defined(X)
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif
int main()
{
    std::cout << s << std::endl;
}
```