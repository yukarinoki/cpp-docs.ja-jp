---
title: コンパイラ エラー C2577 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2577
dev_langs:
- C++
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d9a2b09fc9b8b15c4fc21f5eb537f18f5d3b03e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065817"
---
# <a name="compiler-error-c2577"></a>コンパイラ エラー C2577

'member': デストラクターまたはファイナライザーは、戻り値の型を含めることはできません

デストラクターまたはファイナライザーの値を返すことができません`void`またはその他の種類。 削除、`return`デストラクターの定義からのステートメント。

## <a name="example"></a>例

次の例では、C2577 が生成されます。

```
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```