---
title: 2.7.2 データ共有属性句 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8c53cace8d50f10fe638ea8604c46e457f69ee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392526"
---
# <a name="272-data-sharing-attribute-clauses"></a>2.7.2 データ共有属性句

いくつかのディレクティブは、ユーザーが、リージョンの間の変数の共有の属性を制御できるようにする句を受け入れます。 共有属性句は、句が表示される、ディレクティブの構文範囲内の変数にのみ適用されます。 次の句の一部は、すべてのディレクティブで許可されます。 特定のディレクティブで有効な句の一覧については、ディレクティブを使用して説明します。

変数は、並列操作を実行すると表示される、または動作共有のコンストラクトが見つかりましたが、および共有属性句の変数が指定されていない場合または**threadprivate**ディレクティブ、変数が共有されます。 並列領域の動的範囲内で宣言された静的変数が共有されます。 メモリを割り当てられたヒープ (を使用するなど**malloc()** C または C++ でまたは**新しい**c++ 演算子) が共有します。 (このメモリへのポインター、ただしできますプライベートまたは共有のいずれか。)自動ストレージ存続期間を並行領域の動的範囲内で宣言された変数はプライベートです。

句のほとんどを受け入れる、*変数一覧*が表示されている変数のコンマ区切りのリストの引数。 変数が参照されている場合は、データ共有属性句が、テンプレートから派生した型、他のプログラムでその変数への参照がないと、動作は定義。

ディレクティブの句内に表示されるすべての変数は、表示である必要があります。 句は、必要に応じて繰り返すことが変数可能性がありますが指定されていない 1 つ以上の句でする点を除いて、両方の変数を指定できます、 **firstprivate**と**lastprivate**句。

次のセクションでは、データ共有属性句について説明します。

- **プライベート**、[セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 ページにします。

- **firstprivate**、[セクション 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) [26] ページ。

- **lastprivate**、[セクション 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) [27] ページ。

- **共有**、[セクション 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) [27] ページ。

- **既定**、[セクション 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) 28 ページ。

- **削減**、[セクション 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) 28 ページ。

- **copyin**、[セクション 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) 31 ページにします。

- **copyprivate**、[セクション 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) 32 ページ。