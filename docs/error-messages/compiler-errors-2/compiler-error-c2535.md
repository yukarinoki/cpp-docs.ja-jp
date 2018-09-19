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
ms.openlocfilehash: 98e1920b2163a318fbdba3b64d56bf74a8cd809f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085902"
---
# <a name="compiler-error-c2535"></a>コンパイラ エラー C2535

'identifier' : メンバー関数は、既に定義または宣言されています。

このエラーは、オーバーロードされた関数の定義または宣言で、同じ仮パラメーター リストを繰り返し使用した場合に発生します。

Dispose 関数が原因で C2535 が発生した場合は、次を参照してください。[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)詳細についてはします。

ATL プロジェクトをコンパイルする場合は、サポート技術情報の「PRB: C2535 Error When Compiling ATL Project with Visual C++ 6.0 (Q241852)」を参照してください。

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