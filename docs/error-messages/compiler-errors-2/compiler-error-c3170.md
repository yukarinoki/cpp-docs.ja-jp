---
title: コンパイラ エラー C3170 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7a193abcd59c3e9454eec1108f1e3bbb66efcc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070367"
---
# <a name="compiler-error-c3170"></a>コンパイラ エラー C3170

プロジェクト内の別のモジュール識別子を持つことはできません。

[モジュール](../../windows/module-cpp.md)コンパイルされたファイルの 2 つの異なる名前を持つ属性が見つかりました。 1 つだけの一意な`module`コンパイルごとに属性を指定できます。

同じ`module`属性を 1 つ以上のソース コード ファイルで指定できます。

たとえば、次のモジュールの属性が見つかった場合します。

```
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

この場合、次のようになります。

```
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

コンパイラが生成 C3170 (別の名前に注意してください)。