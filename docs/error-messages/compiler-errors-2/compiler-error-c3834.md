---
title: コンパイラ エラー C3834 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3834
dev_langs:
- C++
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1032c8210cc3df8f9000452ebe18576a10cf5437
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072759"
---
# <a name="compiler-error-c3834"></a>コンパイラ エラー C3834

不正の明示的な; ピンされたポインターへキャストピンされたローカル変数を使用して、代わりに

固定ポインターに明示的なキャストは許可されません。

## <a name="example"></a>例

次の例では、C3834 が生成されます。

```
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
