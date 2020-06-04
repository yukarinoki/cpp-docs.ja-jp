---
title: コンパイラ エラー C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: 44356fb1a1818a02102d23e6b308457f2f39506b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200513"
---
# <a name="compiler-error-c3641"></a>コンパイラ エラー C3641

> '*function*':/clr: pure または/clr: safe と共にコンパイルされた関数の呼び出し規約 ' calling_convention ' が無効です

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

[/Clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)と共に使用できるのは[__clrcall](../../cpp/clrcall.md)呼び出し規約だけです。

## <a name="example"></a>例

次の例では、C3641 が生成されます。

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```
