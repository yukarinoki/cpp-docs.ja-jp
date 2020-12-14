---
description: 詳細については、「コンパイラエラー C3172」を参照してください。
title: コンパイラエラー C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: d8ce88960e725266723c3c37cd9bfbbbd342027b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242172"
---
# <a name="compiler-error-c3172"></a>コンパイラエラー C3172

' module_name ': プロジェクトで異なる idl_module 属性を指定することはできません

同じ名前の、またはパラメーターが異なる[idl_module](../../windows/attributes/idl-module.md)属性が、 `dllname` コンパイルの `version` 2 つのファイルに見つかりました。 コンパイルごとに指定できる一意の属性は1つだけ `idl_module` です。

複数 `idl_module` のソースコードファイルで、同一の属性を指定できます。

たとえば、次のような属性が見つかったとし `idl_module` ます。

```cpp
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

この場合、次のようになります。

```cpp
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

コンパイラは C3172 を生成します (異なるバージョンの値に注意してください)。
