---
title: コンパイラ エラー C3161 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11396ccad33489b41d18759ba4d2f00b445e94a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136076"
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