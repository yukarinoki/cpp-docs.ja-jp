---
title: コンパイラ エラー C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 50148f4fb5c3af33d8de8b005f75f491b0540271
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225502"
---
# <a name="compiler-error-c2388"></a>コンパイラ エラー C2388

' symbol ': シンボルを __declspec (appdomain) と \_ _declspec (process) の両方で宣言することはできません

`appdomain`および修飾子は、 `process` **`__declspec`** 同じシンボルでは使用できません。 変数のストレージは、プロセスごとまたはアプリケーション ドメインごとに存在します。

詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。

次の例では C2388 が生成されます。

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
