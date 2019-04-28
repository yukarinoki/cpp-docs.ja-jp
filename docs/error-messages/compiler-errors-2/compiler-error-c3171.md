---
title: コンパイラ エラー C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 602c9ca1051646fca2c5788c036354047fad2522
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175440"
---
# <a name="compiler-error-c3171"></a>コンパイラ エラー C3171

'module': プロジェクトで異なるモジュールの属性を指定することはできません

[モジュール](../../windows/module-cpp.md)コンパイルされたファイルの 2 つの異なるパラメーター リストを持つ属性が見つかりました。 1 つだけの一意な`module`コンパイルごとに属性を指定できます。

同じ`module`属性を 1 つ以上のソース コード ファイルで指定できます。

たとえば場合、次`module`属性が見つかりました。

```
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

この場合、次のようになります。

```
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

コンパイラが生成 C3171 (別のバージョンの値に注意してください)。