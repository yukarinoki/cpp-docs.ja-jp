---
description: 詳細については、「コンパイラエラー C3161」を参照してください。
title: コンパイラエラー C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 4e45d64e1c1f318a126122148c2dd8e3ddb9c5af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203966"
---
# <a name="compiler-error-c3161"></a>コンパイラエラー C3161

' interface ': インターフェイスでクラス、構造体、共用体、またはインターフェイスを入れ子にすることはできません。クラス、構造体、または共用体にインターフェイスを入れ子にすることは無効です

[__Interface](../../cpp/interface.md)は、グローバルスコープまたは名前空間内でのみ使用できます。 クラス、構造体、または共用体は、インターフェイスには記述できません。

## <a name="example"></a>例

次の例では、C3161 が生成されます。

```cpp
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```
