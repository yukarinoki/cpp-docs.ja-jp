---
description: 詳細については、「コンパイラエラー C2351」を参照してください。
title: コンパイラ エラー C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: ae8cf10cff4a345ee067519d250210f72e6690f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145484"
---
# <a name="compiler-error-c2351"></a>コンパイラ エラー C2351

互換性のために残されている C++ コンストラクター初期化構文

コンストラクターの新しいスタイルの初期化リストでは、基底クラスが唯一の場合でも、各直接基底クラスに明示的に名前を指定する必要があります。

次の例では、C2351 が生成されます。

```cpp
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```
