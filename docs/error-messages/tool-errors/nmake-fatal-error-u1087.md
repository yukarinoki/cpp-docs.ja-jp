---
description: 詳細については、「NMAKE の致命的なエラー U1087」を参照してください。
title: NMAKE の致命的なエラー U1087
ms.date: 11/04/2016
f1_keywords:
- U1087
helpviewer_keywords:
- U1087
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
ms.openlocfilehash: 70b9254f04b0e0042da835e7482b4f0314224b01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345369"
---
# <a name="nmake-fatal-error-u1087"></a>NMAKE の致命的なエラー U1087

同じターゲットに対して: と:: の依存関係を持つことはできません

1つのコロン (**:**) と2つのコロン () の依存関係の両方でターゲットを指定することはできません `::` 。

複数の記述ブロックでターゲットを指定するには、 `::` 各依存関係行でを使用します。
