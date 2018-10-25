---
title: 別のテーブルに行への参照が含まれている場合は、列を更新します |Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 7998897c80e392326213324804c1809656e051f3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071824"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>行への参照が別のテーブルにある場合に列を更新する方法

一部のプロバイダーは列を行の変更で検出できますが、多くのプロバイダーのことはできません。 その結果、列を更新することができます、エラー発生を更新しようとしている行への参照がある場合。 この問題を解決するには、変更する列のみを保持している別のアクセサーを作成します。 そのアクセサーの数を渡して`SetData`します。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)