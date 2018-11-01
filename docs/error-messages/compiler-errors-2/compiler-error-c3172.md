---
title: コンパイラ エラー C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 5c9c1561b63c740b9f7f5d85b2bf3e04de2542c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514947"
---
# <a name="compiler-error-c3172"></a>コンパイラ エラー C3172

'モジュール名': プロジェクトで異なる idl_module の属性を指定することはできません

[idl_module](../../windows/idl-module.md)属性と同じ名前が異なる`dllname`または`version`パラメーターが 2 つのコンパイル時にファイルに見つかりませんでした。 1 つだけの一意な`idl_module`コンパイルごとに属性を指定できます。

同じ`idl_module`属性を 1 つ以上のソース コード ファイルで指定できます。

たとえば場合、次`idl_module`属性が見つかりました。

```
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

この場合、次のようになります。

```
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

コンパイラが生成 C3172 (別のバージョンの値に注意してください)。