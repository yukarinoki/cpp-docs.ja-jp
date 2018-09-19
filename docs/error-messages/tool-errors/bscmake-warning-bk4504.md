---
title: BSCMAKE の警告 BK4504 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8a2da8903dade37faf3b14175b65f3169efd908
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049770"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE の警告 BK4504

ファイルには、参照が多すぎます; が含まれています。このソースからさらに参照を無視します。

.Cpp ファイルには、64,000 を超えるシンボル参照が含まれています。 BSCMAKE では、ファイルで 64,000 の参照が発生したとき、に、それ以上のすべての参照を無視します。

問題を修正する 2 つのファイルに分割またはのいずれかがより少ない 64,000 以上のファイルのシンボル参照、またはを使用して、`#pragma component(browser)`プリプロセッサ ディレクティブの特定の参照用に生成されたシンボルを制限します。 詳細については、次を参照してください。[コンポーネント](../../preprocessor/component.md)します。