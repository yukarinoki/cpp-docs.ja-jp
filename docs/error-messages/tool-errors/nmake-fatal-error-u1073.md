---
title: NMAKE の致命的なエラー U1073 |Microsoft Docs
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
ms.openlocfilehash: 4c309ed94cd1c984406e0d21f0139e35c6e41d7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053942"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE の致命的なエラー U1073

'targetname' を作成する方法がわからない

指定されたターゲットが存在しないと、実行するコマンドまたは推論規則を適用はありません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ターゲット名のスペルを確認します。

1. 場合*targetname* 、疑似ターゲットは、別の記述ブロックのターゲットとして指定します。

1. 場合*targetname*マクロの呼び出しは、null 文字列に展開されないことを確認します。