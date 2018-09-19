---
title: コンパイラの警告 (レベル 1) C4377 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 613ebe183b61c6b9894ed3b726f90061e2b24ef6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047175"
---
# <a name="compiler-warning-level-1-c4377"></a>コンパイラの警告 (レベル 1) C4377

ネイティブ型は既定ではプライベート-d1PrivateNativeTypes が非推奨とされます

以前のリリースではアセンブリのネイティブ型がパブリックでは、既定値、および内部のドキュメントに未記載のコンパイラ オプション (**/d1PrivateNativeTypes**) それらをプライベートにするために使用されました。

すべての型をネイティブと、CLR アセンブリでは、既定でプライベートになったため、 **/d1PrivateNativeTypes**が不要になった。

## <a name="example"></a>例

次の例では、C4377 が生成されます。

```
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```