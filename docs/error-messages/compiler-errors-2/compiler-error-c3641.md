---
description: 詳細については、「コンパイラエラー C3641」を参照してください。
title: コンパイラ エラー C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: 391994a5207fe27cea0b33e6d03e5a1fdc30f6c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239104"
---
# <a name="compiler-error-c3641"></a>コンパイラ エラー C3641

> '*function*':/clr: pure または/clr: safe と共にコンパイルされた関数の呼び出し規約 ' calling_convention ' が無効です

## <a name="remarks"></a>解説

**/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

[/Clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)と共に使用できるのは[__clrcall](../../cpp/clrcall.md)呼び出し規約だけです。

## <a name="example"></a>例

次の例では、C3641 が生成されます。

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```
