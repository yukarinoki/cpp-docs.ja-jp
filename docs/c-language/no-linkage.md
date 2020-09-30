---
title: リンケージなし
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: 69ead5d12d6689370e9ae04a54d5f5a8db06eca5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500744"
---
# <a name="no-linkage"></a>リンケージなし

ブロック内の識別子の宣言に **`extern`** ストレージクラス指定子が含まれていない場合、その識別子はリンケージを持たず、関数に対して一意になります。

次の識別子にはリンケージがありません。

- オブジェクトまたは関数以外として宣言された識別子

- 関数パラメーターとして宣言された識別子

- **`extern`** ストレージクラス指定子なしで宣言されたオブジェクトのブロック スコープ指定子

識別子にリンケージがない場合、同じスコープ レベルで同じ名前を再度 (宣言子または型指定子で) 宣言すると、シンボルの再定義エラーが発生します。

## <a name="see-also"></a>関連項目

[extern を使用したリンケージの指定](../cpp/extern-cpp.md)
