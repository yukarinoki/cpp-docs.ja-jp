---
title: NMAKE の警告 U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: d59b5656d76025fa56bfc76bad800659f25acf53
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193200"
---
# <a name="nmake-warning-u4004"></a>NMAKE の警告 U4004

ターゲット ' targetname ' に対するルールが多すぎます

1つのコロン ( **:** ) を区切り記号として使用して、指定されたターゲットに複数の説明ブロックが指定されました。 NMAKE は、最初の説明ブロックのコマンドを実行し、後のブロックは無視します。

複数の依存関係で同じターゲットを指定するには、各依存関係行の区切り記号として2つのコロン (`::`) を使用します。
