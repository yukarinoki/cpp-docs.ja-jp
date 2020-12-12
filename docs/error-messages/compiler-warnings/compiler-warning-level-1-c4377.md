---
description: '詳細情報: コンパイラの警告 (レベル 1) C4377'
title: コンパイラの警告 (レベル 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: 674bfb69a20c901f20509a7359ed408b0e38f479
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185701"
---
# <a name="compiler-warning-level-1-c4377"></a>コンパイラの警告 (レベル 1) C4377

ネイティブ型は、既定ではプライベートです。-d1PrivateNativeTypes は非推奨です

以前のリリースでは、アセンブリ内のネイティブ型は既定でパブリックになっており、非公開にするためにドキュメントに記載されていないコンパイラオプション (**/d1PrivateNativeTypes**) が使用されていました。

ネイティブと CLR のすべての型は、アセンブリで既定でプライベートになったため、 **/d1PrivateNativeTypes** は不要になりました。

## <a name="example"></a>例

次の例では、C4377 が生成されます。

```cpp
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```
