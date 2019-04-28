---
title: コンパイラ エラー C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: 5ef39e4580601dd90b5695d9115902bb5b834409
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174706"
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