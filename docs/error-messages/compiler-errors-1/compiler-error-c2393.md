---
title: コンパイラ エラー C2393 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 057537c8efcf6e827d9ac9aaf36c0eace6d24156
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704031"
---
# <a name="compiler-error-c2393"></a>コンパイラ エラー C2393

> '*シンボル*': appdomain ごとのシンボルをセグメントに割り当てることはできません'*セグメント*'

## <a name="remarks"></a>コメント

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

使用[appdomain](../../cpp/appdomain.md)変数を使ってコンパイルすることを意味する **/clr: 純粋な**または **/clr:safe**、安全なまたは純粋なイメージは、データ セグメントを含めることはできません。

参照してください[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C2393 を生成します。 この問題を解決するには、データ セグメントを作成できません。

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```