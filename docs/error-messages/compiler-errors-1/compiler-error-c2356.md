---
title: コンパイラ エラー C2356 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2356
dev_langs:
- C++
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfad1703b36e1cd995207d35b99b323c883f828
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065414"
---
# <a name="compiler-error-c2356"></a>コンパイラ エラー C2356

初期化セグメントは翻訳単位の間で変更する必要があります。

以下の原因が考えられます。

- `#pragma init_seg` セグメントの初期化コードに続く

- `#pragma init_seg` 別の前に `#pragma init_seg`

を解決するには、モジュールの先頭にセグメントの初期化コードを移動します。 複数の領域を初期化する場合は、それらを個別のモジュールを移動します。

次の例では、C2356 が生成されます。

```
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```