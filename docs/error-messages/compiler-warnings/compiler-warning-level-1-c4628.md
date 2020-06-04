---
title: コンパイラの警告 (レベル 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: affb2b5231d3745d4826e92657e355ec99570e7e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199668"
---
# <a name="compiler-warning-level-1-c4628"></a>コンパイラの警告 (レベル 1) C4628

digraphs は -Ze でサポートされていません。 文字のシーケンス 'digraph' は 'char' の代替トークンとして解釈されません。

[/Ze](../../build/reference/za-ze-disable-language-extensions.md)では digraphs はサポートされていません。 この警告の後にエラーが表示されます。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4628 が生成されます。

```cpp
// C4628.cpp
// compile with: /WX
#pragma warning(default : 4628)
int main()
<%   // C4628 <% digraph for {
}
```
