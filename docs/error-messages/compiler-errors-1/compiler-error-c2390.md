---
title: コンパイラ エラー C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 89f6ebb02326413e8dca67d333e555321da4e645
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393637"
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