---
description: 詳細については、「コレクションと列挙子インターフェイスのデザイン原則」を参照してください。
title: コレクションと列挙子インターフェイスの設計 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
ms.openlocfilehash: effd2cce775ef926befc89bb6b72a976d85bdf23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148006"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>コレクションと列挙子のインターフェイスの設計原則

インターフェイスの種類によって、さまざまな設計上の原則があります。

- コレクションインターフェイスは、メソッドを使用してコレクション内の *1 つ* の項目に *ランダム* にアクセスできるようにします。これにより、クライアントは、プロパティを使用して `Item` コレクション内の項目数を検出 `Count` し、多くの場合、クライアントが項目を追加および削除できるようになります。

- 列挙子インターフェイスは、コレクション内の *複数* の項目への *シリアル* アクセスを提供します。このため、クライアントはコレクション内の項目数を検出できません (列挙子が項目を返さなくなるまで)。また、項目を追加または削除する方法は用意されていません。

各種類のインターフェイスは、コレクション内の要素へのアクセスを提供するときに、異なる役割を果たします。

## <a name="see-also"></a>関連項目

[コレクションと列挙子](../atl/atl-collections-and-enumerators.md)
