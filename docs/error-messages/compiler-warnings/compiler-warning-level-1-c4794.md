---
description: '詳細情報: コンパイラの警告 (レベル 1) C4794'
title: コンパイラの警告 (レベル 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: bd43a9fb1f7f2433a4e1d337d49c1921211a9e5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334948"
---
# <a name="compiler-warning-level-1-c4794"></a>コンパイラの警告 (レベル 1) C4794

スレッドのローカル ストレージ変数 'variable' のセグメントが 'section name' から '.tls$' に変更されました

tls 変数を .tls$ で始まっていないセクションに配置するために [#pragma data_seg](../../preprocessor/data-seg.md) を使用しました。

.tls$*x* セクションは、 [__declspec(thread)](../../cpp/thread.md) 変数が定義されているオブジェクト ファイルに存在します。 EXE または DLL の .tls セクションはこれらのセクションから生成されます。

## <a name="example"></a>例

次の例では C4794 が生成されます。

```cpp
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```
