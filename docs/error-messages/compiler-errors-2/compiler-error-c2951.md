---
title: コンパイラ エラー C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: dbc7186edfce6cc12a38fb2fc1dda08ac4a181c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300727"
---
# <a name="compiler-error-c2951"></a>コンパイラ エラー C2951

型宣言が、グローバル名前空間でのみ許可されますが、またはクラス スコープ

ジェネリックまたはテンプレート クラスは、グローバルの外部または名前空間スコープを宣言することはできません。 インクルード ファイル内にジェネリックまたはテンプレート宣言を行った場合は、インクルード ファイルは、グローバル スコープでを確認します。

次の例では、C2951 が生成されます。

```
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951 は、ジェネリックを使用しているときにも発生します。

```
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```