---
title: コンパイラ エラー C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 820a620b7e4414123c56433f84536393834f6fd6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585368"
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