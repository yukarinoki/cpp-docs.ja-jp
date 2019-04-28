---
title: コンパイラ エラー C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 22ecc176036308699c3ad7bd8c015836be910073
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174213"
---
# <a name="compiler-error-c3161"></a>コンパイラ エラー C3161

'interface': クラスを入れ子構造体、共用体、またはインターフェイスのインターフェイスは無効です。クラス、構造体または共用体でインターフェイスを入れ子は無効です。

[_ _Interface](../../cpp/interface.md)グローバル スコープまたは名前空間内でだけ記述できます。 クラス、構造体、または共用体は、インターフェイスではできません。

## <a name="example"></a>例

次の例では、C3161 が生成されます。

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```