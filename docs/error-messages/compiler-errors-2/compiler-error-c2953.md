---
title: コンパイラ エラー C2953
ms.date: 11/04/2016
f1_keywords:
- C2953
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
ms.openlocfilehash: 8fa0e533b23f735f948fdad0ecf11beb3766f452
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591046"
---
# <a name="compiler-error-c2953"></a>コンパイラ エラー C2953

'identifier' : クラス テンプレートは既に定義されています

ソース ファイルを確認し、他の定義のファイルをインクルードします。

次の例では C2953 が生成されます。

```
// C2953.cpp
// compile with: /c
template <class T>  class A {};
template <class T>  class A {};   // C2953
template <class T>  class B {};   // OK
```