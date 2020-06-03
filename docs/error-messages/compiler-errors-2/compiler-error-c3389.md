---
title: コンパイラ エラー C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: b166096390169939f01bcb976a57612f10f7df2e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201137"
---
# <a name="compiler-error-c3389"></a>コンパイラ エラー C3389

> __declspec (*キーワード*) を/clr: pure または/clr: safe と共に使用することはできません

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

使用される[__declspec](../../cpp/declspec.md)修飾子は、プロセスごとの状態を意味します。  [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)は、 [appdomain](../../cpp/appdomain.md)ごとの状態を意味します。  したがって、`keyword` **__declspec**修飾子を指定して変数を宣言し、 **/clr: pure**を指定してコンパイルすることはできません。

## <a name="example"></a>例

次の例では、C3389 が生成されます。

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```
