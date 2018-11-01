---
title: コンパイラ エラー C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: e2b08ef3e46681147c4efd77cbffadb096bbfc16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590460"
---
# <a name="compiler-error-c2492"></a>コンパイラ エラー C2492

'*変数*': スレッド ストレージ存続期間を使用してデータを dll インターフェイスいない可能性があります

変数が宣言された、[スレッド](../../cpp/thread.md)属性し、DLL のインターフェイスします。 アドレス、`thread`変数が不明、実行時まで、DLL のインポートまたはエクスポートにリンクできないようにします。

次の例では、C2492 が生成されます。

```
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```