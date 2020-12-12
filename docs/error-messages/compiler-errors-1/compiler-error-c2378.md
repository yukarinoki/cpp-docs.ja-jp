---
description: 詳細については、「コンパイラエラー C2378」を参照してください。
title: コンパイラ エラー C2378
ms.date: 11/04/2016
f1_keywords:
- C2378
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
ms.openlocfilehash: 2a608cf2aa031da26356ec1b2643fc033ff9ddf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174729"
---
# <a name="compiler-error-c2378"></a>コンパイラ エラー C2378

'identifier': 再定義されています。シンボルは typedef でオーバーロードできません

識別子はとして再定義されました **`typedef`** 。

次の例では C2378 が生成されます。

```cpp
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```
