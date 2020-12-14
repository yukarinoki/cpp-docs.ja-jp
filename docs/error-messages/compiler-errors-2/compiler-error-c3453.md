---
description: 詳細については、「コンパイラエラー C3453」を参照してください。
title: コンパイラ エラー C3453
ms.date: 11/04/2016
f1_keywords:
- C3453
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
ms.openlocfilehash: 2ff1c246dc66d60266f0fc44e134db3ab21605df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315973"
---
# <a name="compiler-error-c3453"></a>コンパイラ エラー C3453

'attribute': 修飾子 'assembly' が一致しなかったため、属性は適用されませんでした

アセンブリ レベルまたはモジュール レベルの属性は、スタンドアロンの命令としてのみ指定できます。

## <a name="example"></a>例

次の例では C3453 が生成されます。

```cpp
// C3453.cpp
// compile with: /clr /c
[assembly:System::CLSCompliant(true)]   // C3453
// try the following line instead
// [assembly:System::CLSCompliant(true)];
ref class X {};
```
