---
description: 詳細については、「コンパイラエラー C2371」を参照してください。
title: コンパイラ エラー C2371
ms.date: 11/04/2016
f1_keywords:
- C2371
helpviewer_keywords:
- C2371
ms.assetid: d383993d-05ef-4e35-8129-3b58a6f7b7b7
ms.openlocfilehash: bc7eb66d0ef56d18b7b032dbef17203f600caa0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239650"
---
# <a name="compiler-error-c2371"></a>コンパイラ エラー C2371

'identifier': 再定義されています。異なる基本型です

識別子が既に宣言されています。

次の例では C2371 が生成されます。

```cpp
// C2371.cpp
int main() {
   int i;
   float i;   // C2371, redefinition
   float f;   // OK
}
```
