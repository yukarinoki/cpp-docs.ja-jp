---
title: コンパイラ エラー C2390 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5de5a9af8f8aa04219f0a7d61162336745fd4bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098215"
---
# <a name="compiler-error-c2390"></a>コンパイラ エラー C2390

'identifier': 'specifier' のストレージ クラス

グローバル スコープ識別子のストレージ クラスが正しくありません。 既定のストレージ クラスは、無効なクラスの代わりに使用されます。

考えられる解決策:

- 識別子が関数の場合は、宣言で`extern`ストレージ。

- 識別子は、仮パラメーターまたはローカル変数には、自動ストレージで宣言します。

- 識別子がグローバル変数の場合は、ストレージ クラスが存在しません (自動ストレージ) を宣言します。

## <a name="example"></a>例

- 次の例では、C2390 が生成されます。

```
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```