---
title: コンパイラ エラー C3353 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63316a5a74c3981ec0f68d949eba654f8d6bbfef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110199"
---
# <a name="compiler-error-c3353"></a>コンパイラ エラー C3353

'delegate': デリゲートはマネージド型または WinRT 型のグローバル関数またはメンバー関数からのみ作成できます

使用して、デリゲート宣言、[委任](../../windows/delegate-cpp-component-extensions.md)キーワードは、グローバル スコープでのみ宣言できます。

次の例では C3353 が生成されます。

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```