---
title: 別のテーブルには、行への参照が含まれている場合は、列を更新します |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 17d260f522432a78729c9998c518398dfa41275a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>行への参照が別のテーブルにある場合に列を更新する方法
一部のプロバイダーは、行の変更のどの列を検出できますが、多くのプロバイダーができません。 その結果、列の更新時に発生するエラーを更新しようとしている行への参照があります。 この問題を解決するには、変更する列のみを含む別のアクセサーを作成します。 アクセサーにはその数を渡す`SetData`です。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)