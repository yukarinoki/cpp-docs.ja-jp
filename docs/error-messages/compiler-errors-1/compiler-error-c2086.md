---
title: コンパイラ エラー C2086 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0e0d8b105d58b0585bc31b8d340d3d7ba5fb29e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029846"
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