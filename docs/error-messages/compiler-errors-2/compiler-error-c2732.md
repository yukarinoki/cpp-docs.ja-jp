---
description: 詳細については、「コンパイラエラー C2732」を参照してください。
title: コンパイラエラー C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 1ca97fbf46685af1df37b8caf82a03effc1ec6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123215"
---
# <a name="compiler-error-c2732"></a>コンパイラエラー C2732

リンケージ指定は、別の 'function' に対する指定と矛盾しています。

関数は、別のリンケージ指定子で既に宣言されています。

このエラーは、インクルード ファイルに含まれるリンケージ指定子が異なることが原因で発生する可能性があります。

このエラーを修正するには、 **`extern`** リンケージが一致するようにステートメントを変更します。 具体的には、`extern "C"` ブロックの `#include` ディレクティブをラップしないでください。

## <a name="example"></a>例

次の例では、C2732 エラーが生成されます。

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
