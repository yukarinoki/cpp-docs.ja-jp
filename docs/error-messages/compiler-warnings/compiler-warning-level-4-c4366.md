---
title: コンパイラの警告 (レベル 4) C4366 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4366
dev_langs:
- C++
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb24c65605857124edf608bec88f1399d9df607d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047045"
---
# <a name="compiler-warning-level-4-c4366"></a>コンパイラの警告 (レベル 4) C4366

単項 'operator' 演算子の結果を配置できない可能性があります。

構造体のメンバーまでできません固定パッキングのため、コンパイラは警告ときにアラインされたポインター、メンバーのアドレスが割り当てられています。 既定では、すべてのポインターを配置します。

C4366 を解決するには、構造体のアラインメントを変更またはのいずれかにポインターを宣言、 [_ _unaligned](../../cpp/unaligned.md)キーワード。

詳細についてを参照してください _ _unaligned と[パック](../../preprocessor/pack.md)します。

## <a name="example"></a>例

次の例では、C4366 が生成されます。

```
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```