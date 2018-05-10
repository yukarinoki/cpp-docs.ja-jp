---
title: 2.7.2 データ共有属性句 |Microsoft ドキュメント
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
ms.openlocfilehash: ecc6efac6e3d7356e51dc0ec57009ca9e5a71890
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="272-data-sharing-attribute-clauses"></a>2.7.2 データ共有属性句
いくつかのディレクティブには、ユーザーが、領域の間の変数の共有の属性を制御できるようにする句がそのまま使用します。 共有属性句は、句が表示されます、ディレクティブの構文の範囲内の変数にのみ適用されます。 次の句の一部は、すべてのディレクティブで許可されます。 特定のディレクティブでは有効では、句の一覧については、ディレクティブを使用して説明します。  
  
 変数は並列操作を実行すると表示される、または動作共有のコンストラクトが見つかりましたが、および変数が共有属性句で指定されていない場合または**threadprivate**ディレクティブ、変数が共有されます。 並列領域の動的範囲内で宣言された静的変数が共有されます。 メモリを割り当てられたヒープ (を使用するなど、 **malloc()** C または C++ で、または**新しい**C++ では演算子) が共有します。 (このメモリへのポインターただし、可能プライベートまたは共有のいずれかです。)自動ストレージ存続期間が、並列領域の動的範囲内で宣言された変数はプライベートです。  
  
 句のほとんどを受け入れる、*変数一覧*引数、表示されている変数のコンマ区切りの一覧です。 変数が参照されている場合、データ共有属性句には、テンプレートから派生した型と、プログラムでその変数を他の参照がない、動作は未定義です。  
  
 ディレクティブの句内に表示されるすべての変数を表示する必要があります。 必要に応じて、句を繰り返すことがありますが、変数は指定できません、1 つ以上の句の両方で、変数が指定する点を除いて、 **firstprivate**と**lastprivate**句。  
  
 次のセクションでは、データ共有属性句について説明します。  
  
-   **プライベート**、[セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) [25] ページ。  
  
-   **firstprivate**、[セクション 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) [26] ページ。  
  
-   **lastprivate**、[セクション 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) [27] ページ。  
  
-   **共有**、[セクション 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) [27] ページ。  
  
-   **既定**、[セクション 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) 28 ページ。  
  
-   **reduction**、[セクション 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) 28 ページ。  
  
-   **copyin**、[セクション 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) [31] ページ。  
  
-   **copyprivate**、[セクション 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) [32] ページ。