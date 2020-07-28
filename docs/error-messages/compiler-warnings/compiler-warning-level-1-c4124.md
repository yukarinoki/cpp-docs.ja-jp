---
title: コンパイラの警告 (レベル 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 59860bef108a3cd3e8bbbc6ff0790e17dbdaa0d4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214491"
---
# <a name="compiler-warning-level-1-c4124"></a>コンパイラの警告 (レベル 1) C4124

スタックチェックを使用した __fastcall は効率的ではありません

キーワードは、 **`__fastcall`** スタックチェックが有効になっているときに使用されました。

この **`__fastcall`** 規則はより高速なコードを生成しますが、スタックチェックによってコードが遅くなります。 を使用する場合は **`__fastcall`** 、 **check_stack**プラグマまたは/Gs. を使用してスタックチェックをオフにします。

この警告は、これらの条件下で宣言された最初の関数に対してのみ発行されます。
