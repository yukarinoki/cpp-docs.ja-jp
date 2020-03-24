---
title: コンパイラの警告 (レベル 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 6408185c99a54d5411fa5b1058cd5ec09d3326d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176313"
---
# <a name="compiler-warning-level-1-c4124"></a>コンパイラの警告 (レベル 1) C4124

スタックチェックを使用した __fastcall は効率的ではありません

スタックチェックが有効になっているときに、`__fastcall` キーワードが使用されました。

`__fastcall` 規則はより高速なコードを生成しますが、スタックチェックによってコードが遅くなります。 `__fastcall`を使用する場合は、 **check_stack**プラグマまたは/Gs. を使用してスタックチェックを無効にします。

この警告は、これらの条件下で宣言された最初の関数に対してのみ発行されます。
