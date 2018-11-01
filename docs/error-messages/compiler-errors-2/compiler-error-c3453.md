---
title: コンパイラ エラー C3453
ms.date: 11/04/2016
f1_keywords:
- C3453
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
ms.openlocfilehash: 2b3288d02c611bf6785ca1ea7757e2283d889050
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472723"
---
# <a name="compiler-error-c3453"></a>コンパイラ エラー C3453

'attribute': 修飾子 'assembly' が一致しなかったため、属性は適用されませんでした

アセンブリ レベルまたはモジュール レベルの属性は、スタンドアロンの命令としてのみ指定できます。

## <a name="example"></a>例

次の例では C3453 が生成されます。

```
// C3453.cpp
// compile with: /clr /c
[assembly:System::CLSCompliant(true)]   // C3453
// try the following line instead
// [assembly:System::CLSCompliant(true)];
ref class X {};
```