---
title: コンパイラ エラー C2504 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fb11774f65454799761913babb428dc6a471743
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054130"
---
# <a name="compiler-error-c2504"></a>コンパイラ エラー C2504

'class': 基底クラスが定義されていません

基底クラスが宣言が定義されていることはありません。  以下の原因が考えられます。

1. インクルード ファイルがありません。

1. 外部の基本クラスの宣言[extern](../../cpp/using-extern-to-specify-linkage.md)します。

次の例では、C2504 が生成されます。

```
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