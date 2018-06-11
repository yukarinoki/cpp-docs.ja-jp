---
title: コンパイラ エラー C3641 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99aef6bcfd8ac7ea89cb62fda37c7aec012e16de
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704946"
---
# <a name="compiler-error-c3641"></a>コンパイラ エラー C3641

> '*関数*': の呼び出し規約 'calling_convention'/clr でコンパイルされた関数が無効です:/clr:pure または/clr:safe

## <a name="remarks"></a>コメント

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

のみ[_ _clrcall](../../cpp/clrcall.md)と呼び出し規約が許可されている[/clr: 純粋な](../../build/reference/clr-common-language-runtime-compilation.md)します。

## <a name="example"></a>例

次の例では、C3641 が生成されます。

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```