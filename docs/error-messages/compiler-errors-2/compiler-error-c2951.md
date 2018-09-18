---
title: コンパイラ エラー C2951 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2951
dev_langs:
- C++
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6757256f08c5c1ed0a35fbf1c2a70776a4f2936
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074670"
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