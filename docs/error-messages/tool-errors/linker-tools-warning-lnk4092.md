---
description: 詳細については、「リンカーツールの警告 LNK4092」を参照してください。
title: リンカー ツールの警告 LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 6ef835981a8ed7921147697d6ed9fc79ceeb7033
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210011"
---
# <a name="linker-tools-warning-lnk4092"></a>リンカー ツールの警告 LNK4092

共有書き込みセクション ' section ' に再配置が含まれています。イメージが正しく実行されない可能性があります

リンカーは、潜在的な重大な問題を警告するための共有セクションがある場合に、この警告を出力します。

複数のプロセス間でデータを共有する方法の1つは、セクションを "共有" としてマークすることです。 ただし、セクションを共有としてマークすると、問題が発生する可能性があります。 たとえば、次のような宣言を共有データセクションに含む DLL があるとします。

```
int var = 1;
int *pvar = &var;
```

リンカーは `pvar` dll がメモリに読み込まれている場所に依存しているため、dll に再配置レコードが配置されるため、リンカーは解決できません。 DLL がメモリに読み込まれると、のアドレスを `var` 解決して割り当てることができ `pvar` ます。 別のプロセスが同じ DLL を読み込むが、同じアドレスに読み込むことができない場合、のアドレスの再配置は `var` 2 番目のプロセスに対して更新され、最初のプロセスのアドレス空間は間違ったアドレスを指します。
