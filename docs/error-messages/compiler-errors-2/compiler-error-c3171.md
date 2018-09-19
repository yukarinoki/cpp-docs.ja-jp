---
title: コンパイラ エラー C3171 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3171
dev_langs:
- C++
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32c58f2ecd9651c347f45c29139ffe0ed65a6e3b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082262"
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