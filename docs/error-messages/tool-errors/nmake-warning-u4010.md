---
description: 詳細については、「NMAKE Warning U4010」を参照してください。
title: NMAKE の警告 U4010
ms.date: 11/04/2016
f1_keywords:
- U4010
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
ms.openlocfilehash: d0c72044576ebf3441fdec7980c933edec671097
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334790"
---
# <a name="nmake-warning-u4010"></a>NMAKE の警告 U4010

' target ': ビルドに失敗しました。/K が指定されました。続行します...

指定されたターゲットのコマンドブロック内のコマンドが、0以外の終了コードを返しました。 /K オプションは、ビルドの関連しない部分の処理を続行し、NMAKE セッションが終了したときに終了コード1を発行するように NMAKE に指示しました。

指定されたターゲットが、それ自体が別のターゲットに依存している場合、NMAKE はこの警告の後に警告 [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) を発行します。
