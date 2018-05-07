---
title: NMAKE の致命的なエラー U1073 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dde9ca2f4a15edf6599dcc31b39d9411645f2a6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE の致命的なエラー U1073
'targetname' を作成する方法が分かりません  
  
 指定した対象が存在しないと、実行するコマンドまたは推論規則を適用はありません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ターゲットの名前のスペルを確認します。  
  
2.  場合*targetname* 、疑似ターゲットは、別の記述ブロック対象として指定します。  
  
3.  場合*targetname*マクロの呼び出しは、null 文字列を展開しないことを確認します。