---
title: コンパイラ エラー C2732 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2732
dev_langs:
- C++
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 040fd73bcb69ef032d5c6150bb157337f34a2088
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079662"
---
# <a name="compiler-error-c2732"></a>コンパイラ エラー C2732

リンケージ指定は、別の 'function' に対する指定と矛盾しています。

関数は、別のリンケージ指定子で既に宣言されています。

このエラーは、インクルード ファイルに含まれるリンケージ指定子が異なることが原因で発生する可能性があります。

このエラーを修正するには、`extern` ステートメントを変更してリンケージが一致するようにします。 具体的には、`extern "C"` ブロックの `#include` ディレクティブをラップしないでください。

## <a name="example"></a>例

次の例では、C2732 エラーが生成されます。

```
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```