---
title: NMAKE の警告 U4010 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4010
dev_langs:
- C++
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a640245db460f4cd8cd658c097955a69a59d1fb7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117503"
---
# <a name="nmake-warning-u4010"></a>NMAKE の警告 U4010

'target': ビルドに失敗しました。/K 指定すると、続行しています.

指定したターゲットのコマンド ブロックのコマンドでは、0 以外の終了コードが返されます。 /K オプションでは、NMAKE (nmake の) セッションが終了すると、終了コード 1 を発行して、ビルドの関連付けられていない部分の処理を続行するように指示します。

NMAKE が警告を発行する場合は、指定されたターゲットは、自体の別のターゲットの依存[U4011](../../error-messages/tool-errors/nmake-warning-u4011.md)この警告の後にします。