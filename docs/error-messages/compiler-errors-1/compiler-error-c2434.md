---
description: 詳細については、「コンパイラエラー C2434」を参照してください。
title: コンパイラエラー C2434
ms.date: 11/04/2016
f1_keywords:
- C2434
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
ms.openlocfilehash: e24eb3fdf2ae60dadc270bed1bdda251acfc70a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189965"
---
# <a name="compiler-error-c2434"></a>コンパイラエラー C2434

> '*symbol*': __declspec (process) で宣言されたシンボルを/clr: pure モードで動的に初期化することはできません

## <a name="remarks"></a>解説

**/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

**/Clr: pure** の下でプロセスごとの変数を動的に初期化することはできません。 詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) と [プロセス](../../cpp/process.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2434 が生成されます。 この問題を解決するには、定数を使用して変数を初期化 `process` します。

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```
