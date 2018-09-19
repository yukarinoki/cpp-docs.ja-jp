---
title: コンパイラ エラー C2430 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2430
dev_langs:
- C++
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 102e7082a3fc1cfd96db5c38832e3ebb91ee742c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054455"
---
# <a name="compiler-error-c2430"></a>コンパイラ エラー C2430

1 つ以上のインデックスが 'identifier' の登録します。

1 つ以上の登録でスケーリングします。 コンパイラは、インデックスのスケーリングをサポートしていますが、レジスタは 1 つまでしかスケールすることができます。

## <a name="example"></a>例

次の例では、C2430 が生成されます。

```
// C2430.cpp
// processor: x86
int main() {
   _asm mov eax, [ebx*2+ecx*4] // C2430
}
```