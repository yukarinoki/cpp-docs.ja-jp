---
title: NMAKE の警告 U4004 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a89bb8abf212c8a0ffa9fb40fe5d3ea43307a08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016651"
---
# <a name="nmake-warning-u4004"></a>NMAKE の警告 U4004

ターゲット 'targetname' のルールが多すぎます

1 つ以上の記述ブロックでは、1 つのコロンを使用して、指定されたターゲットが指定されました (**:**) 区切り記号として。 NMAKE では、最初の記述ブロックのコマンドを実行し、後のブロックを無視します。

複数の依存関係で同じターゲットを指定する 2 つのコロンを使用して、(`::`) 依存関係の行ごとに、区切り文字として。