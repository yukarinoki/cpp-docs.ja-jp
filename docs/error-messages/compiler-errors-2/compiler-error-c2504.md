---
description: 詳細については、「コンパイラエラー C2504」を参照してください。
title: コンパイラ エラー C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 2a2269d750673a912096b497c10a9b112c23207c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213027"
---
# <a name="compiler-error-c2504"></a>コンパイラ エラー C2504

' class ': 基底クラスが定義されていません。

基底クラスが宣言されていますが、定義されていません。  次の原因が考えられます。

1. インクルードファイルがありません。

1. 外部基底クラスが [extern](../../cpp/extern-cpp.md)で宣言されていません。

次の例では、C2504 が生成されます。

```cpp
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

わかりました

```
class C{};
class D : public C {};
```
