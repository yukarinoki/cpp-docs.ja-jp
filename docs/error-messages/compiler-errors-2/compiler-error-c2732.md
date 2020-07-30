---
title: コンパイラエラー C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 78be424040c7315271d0880c6678584f698b5be8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218183"
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
