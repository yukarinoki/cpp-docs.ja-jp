---
description: 詳細については、「コンパイラエラー C3233」を参照してください。
title: コンパイラ エラー C3233
ms.date: 11/04/2016
f1_keywords:
- C3233
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
ms.openlocfilehash: 825269c96e596a53b9f1852ce50741f9a5d70e6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311995"
---
# <a name="compiler-error-c3233"></a>コンパイラ エラー C3233

'type': ジェネリック型パラメーターは既に制約されています

複数の `where` 句でジェネリック パラメーターを制約することは無効です。

次の例では C3233 が生成されます。

```cpp
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```
