---
title: コンパイラ エラー C3389 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b540f87458c75ddf7d57626b6251248652b96213
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704306"
---
# <a name="compiler-error-c3389"></a>コンパイラ エラー C3389

> _ _declspec (*キーワード*) では使用できません:/clr:pure または/clr:safe

## <a name="remarks"></a>コメント

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

A [_ _declspec](../../cpp/declspec.md)修飾子の使用を意味するプロセスの状態ごとです。  [/clr: 純粋な](../../build/reference/clr-common-language-runtime-compilation.md)意味、あたり[appdomain](../../cpp/appdomain.md)状態です。  そのために変数を宣言する、 `keyword` **_ _declspec**修飾子と指定してコンパイル **/clr: 純粋な**は許可されていません。

## <a name="example"></a>例

次の例では、C3389 が生成されます。

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```