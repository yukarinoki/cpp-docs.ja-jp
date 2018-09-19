---
title: コンパイラ エラー C2959 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2959
dev_langs:
- C++
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f225dccc917e34fba690064d66cf1cda36219877
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078973"
---
# <a name="compiler-error-c2959"></a>コンパイラ エラー C2959

テンプレートのメンバーはジェネリック クラスまたは関数ではない可能性があります。

詳細については、次を参照してください。 [Windows ランタイムおよびマネージ テンプレート](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)と[ジェネリック](../../windows/generics-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C2959 が生成されます。

```
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```