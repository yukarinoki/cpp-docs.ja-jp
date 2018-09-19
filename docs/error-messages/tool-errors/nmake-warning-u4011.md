---
title: NMAKE の警告 U4011 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1038ee86f76789451565ab6799795c851c95a95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118337"
---
# <a name="nmake-warning-u4011"></a>NMAKE の警告 U4011

'target': 依存ファイルの一部が使用できます。ターゲットはビルドされません。

指定されたターゲットの依存が存在していなかったか、最新でし、の依存を更新するためのコマンドには 0 以外の終了コードが返されます。 /K オプションでは、NMAKE (nmake の) セッションが終了すると、終了コード 1 を発行して、ビルドの関連付けられていない部分の処理を続行するように指示します。

この警告は、前に警告[U4010](../../error-messages/tool-errors/nmake-warning-u4010.md)に作成または更新に失敗した依存します。