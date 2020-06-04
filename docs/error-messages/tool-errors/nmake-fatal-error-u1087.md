---
title: NMAKE の致命的なエラー U1087
ms.date: 11/04/2016
f1_keywords:
- U1087
helpviewer_keywords:
- U1087
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
ms.openlocfilehash: ad6f422f42b2ba284a2886065b6181b879e7c7fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193513"
---
# <a name="nmake-fatal-error-u1087"></a>NMAKE の致命的なエラー U1087

同じターゲットに対して: と:: の依存関係を持つことはできません

1つのコロン ( **:** ) と2つのコロン (`::`) の依存関係の両方でターゲットを指定することはできません。

複数の説明ブロックでターゲットを指定するには、各依存関係行で `::` を使用します。
