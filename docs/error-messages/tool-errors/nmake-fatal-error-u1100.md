---
title: NMAKE の致命的なエラー U1100 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27ffd33a0a80056ee57f5f088823d7f8f6549c24
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135766"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE の致命的なエラー U1100

マクロ 'macroname' はバッチ ルール 'rule' のコンテキストでは無効です。

NMAKE が $ ではない特殊なファイル マクロをバッチ モードの規則のコマンド ブロック直接的または間接的に参照する場合、このエラーを生成 < します。

$< が使用できる唯一のバッチ モードの規則のマクロ。