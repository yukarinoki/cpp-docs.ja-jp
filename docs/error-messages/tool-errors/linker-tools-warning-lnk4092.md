---
title: リンカー ツールの警告 LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 706ab843f4b079b507033af76a7f407816fce820
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183359"
---
# <a name="linker-tools-warning-lnk4092"></a>リンカー ツールの警告 LNK4092

共有書き込みセクション ' section ' に再配置が含まれています。イメージが正しく実行されない可能性があります

リンカーは、潜在的な重大な問題を警告するための共有セクションがある場合に、この警告を出力します。

複数のプロセス間でデータを共有する方法の1つは、セクションを "共有" としてマークすることです。 ただし、セクションを共有としてマークすると、問題が発生する可能性があります。 たとえば、次のような宣言を共有データセクションに含む DLL があるとします。

```
int var = 1;
int *pvar = &var;
```

リンカーは、DLL がメモリに読み込まれた場所に依存しているため、`pvar` を解決できません。そのため、DLL に再配置レコードが配置されます。 DLL がメモリに読み込まれると、`var` のアドレスを解決して割り当て `pvar` ことができます。 別のプロセスが同じ DLL を読み込むが、同じアドレスに読み込むことができない場合、`var` のアドレスの再配置は2番目のプロセスに対して更新され、最初のプロセスのアドレス空間は間違ったアドレスを指します。
