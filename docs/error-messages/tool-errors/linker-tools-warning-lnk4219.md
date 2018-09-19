---
title: リンカー ツールの警告 LNK4219 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4219
dev_langs:
- C++
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: daf097cd8715a7c523e6e8a2ea46714481ca7d2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105212"
---
# <a name="linker-tools-warning-lnk4219"></a>リンカー ツールの警告 LNK4219

フィックス アップ名前 fixup オーバーフロー。 ターゲット 'ターゲット symbol name' がサンクを挿入する範囲外です。

リンカーでは、場所、アドレスまたはオフセットできなかったターゲット シンボルが命令の位置から離れすぎているために、指定された命令に収まるように状況にサンクが挿入されます。

イメージの順序を変更することがあります (を使用して、 [/order](../../build/reference/order-put-functions-in-order.md)オプション、たとえば) 余分なレベルの間接参照を回避するためにします。