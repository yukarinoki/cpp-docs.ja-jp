---
title: リンケージなし
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: a7c9a5b8f0ba92830500e55818093981a044d2df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218807"
---
# <a name="no-linkage"></a>リンケージなし

ブロック内の識別子の宣言に **`extern`** ストレージクラス指定子が含まれていない場合、その識別子はリンケージを持たず、関数に対して一意になります。

次の識別子にはリンケージがありません。

- オブジェクトまたは関数以外として宣言された識別子

- 関数パラメーターとして宣言された識別子

- **`extern`** ストレージクラス指定子なしで宣言されたオブジェクトのブロック スコープ指定子

識別子にリンケージがない場合、同じスコープ レベルで同じ名前を再度 (宣言子または型指定子で) 宣言すると、シンボルの再定義エラーが発生します。

## <a name="see-also"></a>関連項目

[extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)
