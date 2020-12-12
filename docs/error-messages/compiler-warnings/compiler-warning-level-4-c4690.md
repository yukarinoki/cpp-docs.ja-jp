---
description: '詳細情報: コンパイラの警告 (レベル 4) C4690'
title: コンパイラの警告 (レベル 4) C4690
ms.date: 07/03/2018
f1_keywords:
- C4690
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
ms.openlocfilehash: 1f6d3ee3f6ba20207a355350edda99861d10b5f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133848"
---
# <a name="compiler-warning-level-4-c4690"></a>コンパイラの警告 (レベル 4) C4690

> \[ emitidl (pop)]: ポップの数がプッシュよりも多くなっています

## <a name="remarks"></a>解説

[emitidl](../../windows/attributes/emitidl.md) 属性は、プッシュよりも 1 回多くポップされています。

## <a name="example"></a>例

次の例では C4690 警告が生成されます。 この問題を解決するには、属性がプッシュされた回数だけポップされるようにします。

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
