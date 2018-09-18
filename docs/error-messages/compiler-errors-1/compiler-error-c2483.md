---
title: コンパイラ エラー C2483 |Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2483
dev_langs:
- C++
helpviewer_keywords:
- C2483
ms.assetid: 5762b325-914b-442d-a604-e4617ba04038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be2a2caef9e1252bf1ab36253a7f5f715b94d5a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031614"
---
# <a name="compiler-error-c2483"></a>コンパイラ エラー C2483

>'*識別子*': 'thread' コンス トラクターまたはデストラクターを持つオブジェクトを宣言することはできません

このエラー メッセージは、Visual Studio 2015 以降で廃止されています。 以前のバージョンで宣言された変数、`thread`コンス トラクターまたは実行時の評価が必要なその他の式では、属性を初期化できません。 静的な式が初期化に必要な`thread`データ。

## <a name="example"></a>例

次の例では、Visual Studio 2013 および以前のバージョンで C2483 が生成されます。

```cpp
// C2483.cpp
// compile with: /c
__declspec(thread) struct A {
   A(){}
   ~A(){}
} aa;   // C2483 error

__declspec(thread) struct B {} b;   // OK
```

## <a name="see-also"></a>関連項目

[thread](../../cpp/thread.md)