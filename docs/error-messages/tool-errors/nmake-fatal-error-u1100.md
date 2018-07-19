---
title: NMAKE の致命的なエラー U1100 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4ed57c980813c8539fbffed0e41a35048c0571
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319619"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE の致命的なエラー U1100
マクロ 'macroname' はバッチ ルール 'rule' のコンテキストでは無効  
  
 NMAKE が $ ではない特殊なファイル マクロをバッチ モードの規則のコマンドのブロック直接的または間接的に参照する場合、このエラーを生成 < です。  
  
 $< は、使用できる唯一のバッチ モードの規則のマクロです。