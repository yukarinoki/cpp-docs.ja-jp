---
title: コンパイラの警告 (レベル 3) C4637
ms.date: 11/04/2016
f1_keywords:
- C4637
helpviewer_keywords:
- C4637
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
ms.openlocfilehash: 80c55494a391922453f2d89ae26ee5f47dc433b1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815451"
---
# <a name="compiler-warning-level-3-c4637"></a>コンパイラの警告 (レベル 3) C4637

XML ドキュメント コメント ターゲット:\<含める > タグは破棄されます。  理由

構文、 [\<含める >](../../build/reference/include-visual-cpp.md)タグが正しくありません。

次の例では C4637 警告が生成されます。

```
// C4637.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <include file="c:\davedata\jtest\xml_include.doc"/>
   // Try the following line instead:
   // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' />
   void MyMethod() {
   }
};   // C4637
```