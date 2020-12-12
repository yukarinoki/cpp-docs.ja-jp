---
description: 詳細については、「コンパイラエラー C2825」を参照してください。
title: コンパイラ エラー C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: fa72f915a77ec26e6da402ae8ff87ee380f1838c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194580"
---
# <a name="compiler-error-c2825"></a>コンパイラ エラー C2825

var: ':: ' が後に続く場合は、クラスまたは名前空間でなければなりません

修飾名を作成しようとしましたが、失敗しました。

たとえば、関数名が:: で始まる関数宣言がコードに含まれていないことを確認します。

## <a name="example"></a>例

次の例では、C2825 が生成されます。

```cpp
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```
