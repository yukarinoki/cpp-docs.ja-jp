---
description: '詳細情報: コンパイラの警告 (レベル 1) C4124'
title: コンパイラの警告 (レベル 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 97fe65f8513f656d85059714ae598ffad9f7a49c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267392"
---
# <a name="compiler-warning-level-1-c4124"></a>コンパイラの警告 (レベル 1) C4124

スタックチェックを使用した __fastcall は効率的ではありません

キーワードは、 **`__fastcall`** スタックチェックが有効になっているときに使用されました。

この **`__fastcall`** 規則はより高速なコードを生成しますが、スタックチェックによってコードが遅くなります。 を使用する場合は **`__fastcall`** 、 **check_stack** プラグマまたは/Gs. を使用してスタックチェックをオフにします。

この警告は、これらの条件下で宣言された最初の関数に対してのみ発行されます。
