---
title: コンパイラ エラー C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 9ac8f5e5edb1a6ed7314c5b5d125fcc9bfbe67de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378904"
---
# <a name="compiler-error-c2879"></a>コンパイラ エラー C2879

'symbol': 既存の名前空間は、名前を指定できます、代替名前空間のエイリアス定義によってのみ

作成することはできません、[名前空間エイリアス](../../cpp/namespaces-cpp.md#namespace_aliases)名前空間以外のシンボルにします。

次の例では、C2879 が生成されます。

```
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```