---
title: リンケージなし
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: 9775270c5c1fb0b6758f994c432104d75e19d38d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505080"
---
# <a name="no-linkage"></a>リンケージなし

ブロック内の識別子の宣言に `extern` ストレージ クラス指定子が含まれていない場合、その識別子はリンケージを持たず、関数に対して一意になります。

次の識別子にはリンケージがありません。

- オブジェクトまたは関数以外として宣言された識別子

- 関数パラメーターとして宣言された識別子

- `extern` ストレージ クラス指定子なしで宣言されたオブジェクトのブロック スコープ指定子

識別子にリンケージがない場合、同じスコープ レベルで同じ名前を再度 (宣言子または型指定子で) 宣言すると、シンボルの再定義エラーが発生します。

## <a name="see-also"></a>参照

[extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)