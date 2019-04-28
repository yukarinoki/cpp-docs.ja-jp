---
title: コンパイラ エラー C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 094a794627b886abc7db5ba4d74c6fe97ff82461
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216127"
---
# <a name="compiler-error-c2086"></a>コンパイラ エラー C2086

'identifier': 再定義されています

識別子が複数回定義されているまたはそれ以降の宣言と前の 1 つは異なります。

C2086 は、c# アセンブリが参照先のインクリメンタル ビルドの結果もできます。 このエラーを解決するには、c# アセンブリを再構築します。

次の例では、C2086 が生成されます。

```
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```