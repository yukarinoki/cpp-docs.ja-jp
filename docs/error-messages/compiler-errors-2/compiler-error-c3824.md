---
title: コンパイラ エラー C3824 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03d42f80716b81f4409449262af650220b1ad92b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083952"
---
# <a name="compiler-error-c3824"></a>コンパイラ エラー C3824

'member': この型は、(関数のパラメーター、戻り値の型、または静的メンバー) は、このコンテキストで表示されることはできません

固定ポインターの型を返す、関数パラメーターにすることはできませんまたは宣言`static`します。

## <a name="example"></a>例

次の例では、C3824 が生成されます。

```
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
