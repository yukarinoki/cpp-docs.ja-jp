---
title: コンパイラの警告 (レベル 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: d8c89967e0dc900e098ca03d22932451f26a6a0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531022"
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