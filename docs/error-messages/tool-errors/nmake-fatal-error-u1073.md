---
description: 詳細については、「NMAKE の致命的なエラー U1073」を参照してください。
title: NMAKE の致命的なエラー U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: bd622f37720cf5e992a1d82ea97ca1ff50344c0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345447"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE の致命的なエラー U1073

' targetname ' を作成する方法がわかりません

指定されたターゲットは存在しません。実行するコマンドや、適用する推定ルールがありません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ターゲット名のスペルを確認します。

1. *Targetname* が pseudotarget の場合は、別の説明ブロックのターゲットとして指定します。

1. *Targetname* がマクロ呼び出しの場合は、null 文字列に展開されないようにしてください。
