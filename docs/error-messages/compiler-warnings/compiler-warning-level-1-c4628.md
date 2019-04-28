---
title: コンパイラの警告 (レベル 1) C4628
ms.date: 11/04/2016
f1_keywords:
- C4628
helpviewer_keywords:
- C4628
ms.assetid: 20fdc6f8-5f6a-40cc-aff8-c7ccf3d8ec26
ms.openlocfilehash: ebb71155774ce32d6b4fc2b9920fdd31dd466841
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221207"
---
# <a name="compiler-warning-level-1-c4628"></a>コンパイラの警告 (レベル 1) C4628

digraphs は -Ze でサポートされていません。 文字のシーケンス 'digraph' は 'char' の代替トークンとして解釈されません。

Digraphs はではサポートされていない[/Ze](../../build/reference/za-ze-disable-language-extensions.md)します。 この警告は、エラーの後に指定されます。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4628 が生成されます。

```
// C4628.cpp
// compile with: /WX
#pragma warning(default : 4628)
int main()
<%   // C4628 <% digraph for {
}
```