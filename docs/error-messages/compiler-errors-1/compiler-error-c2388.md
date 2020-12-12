---
description: 詳細については、「コンパイラエラー C2388」を参照してください。
title: コンパイラ エラー C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 63a2758b4e214b38c7d999bdc2a33d328709ea67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123982"
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
