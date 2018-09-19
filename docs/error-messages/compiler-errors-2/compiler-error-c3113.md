---
title: コンパイラ エラー C3113 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3113
dev_langs:
- C++
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e830fe5aff3912b48dbf9a633a0537dff4d05c91
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082704"
---
# <a name="compiler-error-c3113"></a>コンパイラ エラー C3113

'structure' がテンプレートまたはジェネリックにすることはできません。

ジェネリック インターフェイスまたは列挙型クラス テンプレートまたはクラスを作成しようとしました。

次の例では、C3113 が生成されます。

```
// C3113.cpp
// compile with: /c
template <class T>
enum E {};   // C3113
// try the following line instead
// class MyClass{};
```