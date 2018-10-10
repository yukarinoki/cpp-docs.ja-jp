---
title: コンパイラ エラー C2535 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d9bb276ded32d8b263e64a8ea70f2c1953ee24b
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890297"
---
# <a name="compiler-error-c2535"></a>コンパイラ エラー C2535

'identifier' : メンバー関数は、既に定義または宣言されています。

このエラーは、オーバーロードされた関数の定義または宣言で、同じ仮パラメーター リストを繰り返し使用した場合に発生します。

Dispose 関数が原因で C2535 が発生した場合は、次を参照してください。[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)詳細についてはします。

次の例では、C2535 が生成されます。

```
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```