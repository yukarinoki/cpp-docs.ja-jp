---
title: NMAKE の致命的なエラー U1099 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3ef75a1435d8c922087fcdd21d1941961bc82cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113384"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE の致命的なエラー U1099

スタック オーバーフロー

処理中のメイクファイルが複雑すぎるため、現在のスタック割り当て (nmake の)。 NMAKE は、0x3000 (12 K) の割り当てが。

NMAKE のスタック割り当てを増やすには、実行、 [editbin/stack](../../build/reference/stack.md)ユーティリティをより大きなスタック オプション。

**editbin/STACK:reserve (nmake の)。実行可能ファイル**

場所*予約*数値を (nmake の) 現在のスタック割り当てを超えています。