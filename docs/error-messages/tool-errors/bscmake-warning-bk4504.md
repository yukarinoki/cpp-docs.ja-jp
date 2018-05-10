---
title: BSCMAKE の警告 BK4504 |Microsoft ドキュメント
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
ms.openlocfilehash: 5a17aa8b4e2a98d3bda5d21ea84962791b8051dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE の警告 BK4504
ファイルには、参照が多すぎます; が含まれています。このソースからさらに参照は無視されます。  
  
 .Cpp ファイルには、複数の 64,000 シンボル参照が含まれています。 BSCMAKE では、ファイルで 64,000 の参照が発生しました、ときにそれ以上のすべての参照は無視されます。  
  
 問題を修正する 2 つのファイルに分割またはより少ない 64,000 を持つ他のファイルのシンボル参照、またはを使用して、`#pragma component(browser)`プリプロセッサ ディレクティブの特定の参照に対して生成されるシンボルを制限します。 詳細については、次を参照してください。[コンポーネント](../../preprocessor/component.md)です。