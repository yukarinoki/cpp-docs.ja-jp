---
title: コンパイラの警告 (レベル 1) C4160
ms.date: 08/27/2018
f1_keywords:
- C4160
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
ms.openlocfilehash: 8eb53d3f00c717df0e657ede3de6dd71d4a0bb47
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176170"
---
# <a name="compiler-warning-level-1-c4160"></a>コンパイラの警告 (レベル 1) C4160

> #<a name="pragma-pop--did-not-find-previously-pushed-identifier-identifier"></a>pragma (pop,...): 以前にプッシュされた識別子 '*identifier*' が見つかりませんでした

## <a name="remarks"></a>解説

ソース コードのプラグマ ステートメントで、プッシュされていない識別子のポップを試みています。 この警告を回避するには、ポップされている識別子が正しくプッシュされていることを確認してください。

## <a name="example"></a>例

次の例では、C4160 を生成し、その修正方法を示しています。

```cpp
// C4160.cpp
// compile with: /W1
#pragma pack(push)

#pragma pack(pop, id)   // C4160
// use identifier when pushing to resolve the warning
// #pragma pack(push, id)

int main() {
}
```
