---
title: コンパイラ エラー C2530 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f41f9ec64e2074ed5e0cd2654f2b6bfec886bc07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103196"
---
# <a name="compiler-error-c2530"></a>コンパイラ エラー C2530

'identifier': 参照を初期化する必要があります

既に宣言されていない限り、宣言されているときに、参照を初期化する必要があります。

- キーワードを使用して[extern](../../cpp/using-extern-to-specify-linkage.md)します。

- クラス、構造体、共用体のメンバーとして (およびコンス トラクターで初期化されます)。

- 関数宣言または定義でパラメーター。

- 関数の戻り値の型。

次の例では、C2530 が生成されます。

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```