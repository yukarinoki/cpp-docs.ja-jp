---
title: コンパイラ エラー C2434 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2434
dev_langs:
- C++
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45f9ccdef84713883c53dab0e7caf3b1519628de
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704228"
---
# <a name="compiler-error-c2434"></a>コンパイラ エラー C2434

> '*シンボル*': __declspec(process) と共に宣言されたシンボルは/clr で動的に初期化できません: 純粋モード

## <a name="remarks"></a>コメント

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

プロセスごとの変数を動的に初期化することはできません **/clr: 純粋な**します。 詳細については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[プロセス](../../cpp/process.md)です。

## <a name="example"></a>例

次の例では、C2434 を生成します。 この問題を解決する定数を使用して初期化`process`変数。

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```