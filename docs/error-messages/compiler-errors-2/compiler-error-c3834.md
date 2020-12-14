---
description: 詳細については、「コンパイラエラー C3834」を参照してください。
title: コンパイラ エラー C3834
ms.date: 11/04/2016
f1_keywords:
- C3834
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
ms.openlocfilehash: 4cf0bc5e3587e77d8ad31fc4e2fd2cf0130aa781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249179"
---
# <a name="compiler-error-c3834"></a>コンパイラ エラー C3834

ピンポインターへの明示的なキャストが無効です。代わりにピン留めされたローカル変数を使用する

ピン留めされたポインターへの明示的なキャストは許可されていません。

## <a name="example"></a>例

次の例では、C3834 が生成されます。

```cpp
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
