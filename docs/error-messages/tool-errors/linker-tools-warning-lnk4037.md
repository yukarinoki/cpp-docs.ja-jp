---
title: リンカー ツールの警告 LNK4037 |Microsoft ドキュメント
ms.custom: ''
ms.date: 10/04/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4037
dev_langs:
- C++
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b87f0a415d6ae7d282e29c2ca67fda043c2a901
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302436"
---
# <a name="linker-tools-warning-lnk4037"></a>リンカー ツールの警告 LNK4037

>'*シンボル*' がありません。 無視されます。

装飾名*シンボル*を使用して順序付けされませんでした、 [/order](../../build/reference/order-put-functions-in-order.md)プログラムで見つかりませんオプションを指定します。 仕様の確認*シンボル*順序応答ファイルにします。 詳細については、次を参照してください。、 [/ORDER (関数の順序に Put)](../../build/reference/order-put-functions-in-order.md)リンカー オプション。

> [!NOTE]
> 静的関数名は、パブリック シンボル名ではないために、リンクで静的関数を注文することはできません。 ときに **/order**は指定が静的である注文の応答ファイル内の各シンボルに対してこのリンカー警告が生成されるか、見つかりませんでした。