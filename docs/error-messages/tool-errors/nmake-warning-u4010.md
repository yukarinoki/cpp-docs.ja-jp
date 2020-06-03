---
title: NMAKE の警告 U4010
ms.date: 11/04/2016
f1_keywords:
- U4010
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
ms.openlocfilehash: f68da1893eec6325ccccfd0e2e2dd0e612f28eb9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193135"
---
# <a name="nmake-warning-u4010"></a>NMAKE の警告 U4010

' target ': ビルドに失敗しました。/K が指定されました。続行します...

指定されたターゲットのコマンドブロック内のコマンドが、0以外の終了コードを返しました。 /K オプションは、ビルドの関連しない部分の処理を続行し、NMAKE セッションが終了したときに終了コード1を発行するように NMAKE に指示しました。

指定されたターゲットが、それ自体が別のターゲットに依存している場合、NMAKE はこの警告の後に警告[U4011](../../error-messages/tool-errors/nmake-warning-u4011.md)を発行します。
