---
title: コンパイラ エラー C3453 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3453
dev_langs:
- C++
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c35c039727cba004db879aea02c086cea4ddcec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068805"
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