---
title: コンパイラ エラー C3155 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3155
dev_langs:
- C++
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b4000c9e7d3f175c243d4d3761216f4acface8f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076477"
---
# <a name="compiler-error-c3155"></a>コンパイラ エラー C3155

属性は、プロパティ インデクサーでは使用できません。

インデックス付きプロパティの宣言が正しくありません。 詳細については、次を参照してください。[方法: プロパティを使用して c++/cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)します。

## <a name="example"></a>例

次の例では、C3155 が生成されます。

```
// C3155.cpp
// compile with: /clr /c
using namespace System;
ref struct R {
   property int F[[ParamArray] int] {   // C3155
   // try the following line instead
   // property int F[ int] {   // OK
      int get(int i) {
         return 0;
      }
   }
};
```