---
title: リンカ ツール エラー LNK1221 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1221
dev_langs:
- C++
helpviewer_keywords:
- LNK1221
ms.assetid: 70654bf9-1520-4fa3-a063-1219dd88abf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6347bc4e7a14f335a006b666e03851fa8979801
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023320"
---
# <a name="linker-tools-error-lnk1221"></a>リンカ ツール エラー LNK1221

サブシステムは推論することはできませんし、定義する必要があります。

リンカーでは、対象とするサブシステムを推論するのに十分な情報はありません。

このエラーを修正するには使用[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)します。