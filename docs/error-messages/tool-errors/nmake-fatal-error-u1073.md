---
title: NMAKE の致命的なエラー U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: 97d44594540d18bf008757506a9e36e6d16d2cd7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182696"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE の致命的なエラー U1073

' targetname ' を作成する方法がわかりません

指定されたターゲットは存在しません。実行するコマンドや、適用する推定ルールがありません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. ターゲット名のスペルを確認します。

1. *Targetname*が pseudotarget の場合は、別の説明ブロックのターゲットとして指定します。

1. *Targetname*がマクロ呼び出しの場合は、null 文字列に展開されないようにしてください。
