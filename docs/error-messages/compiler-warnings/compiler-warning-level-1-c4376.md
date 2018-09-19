---
title: コンパイラの警告 (レベル 1) C4376 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4376
dev_langs:
- C++
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1923f2aed19de5e7f438407c25640821a2fa49c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039622"
---
# <a name="compiler-warning-level-1-c4376"></a>コンパイラの警告 (レベル 1) C4376

アクセス指定子 'old_specifier:' はサポートされていません。'new_specifier:' を使用してください

メタデータの型とメンバーのアクセシビリティを指定する方法の詳細については、次を参照してください[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[メンバーの可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)で[する方法: を定義すると消費クラスと構造体 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)。

## <a name="example"></a>例

次の例では、C4376 が生成されます。

```
// C4376.cpp
// compile with: /clr /W1 /c
public ref class G {
public public:   // C4376
   void m2();
};

public ref class H {
public:   // OK
   void m2();
};
```