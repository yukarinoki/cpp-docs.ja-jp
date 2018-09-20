---
title: 配列、リスト、およびクラスのマップ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8d044f8844fdf46969342d1b4fc5cf2f007c041
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436339"
---
# <a name="array-list-and-map-classes"></a>配列、リスト、マップ クラス

クラス ライブラリをデータの集計を処理するためには、コレクション クラスのグループを提供します-配列、リスト、およびマップなどのさまざまなオブジェクトや定義済みの型を保持することができます。 コレクションは動的にサイズ変更します。 これらのクラスは、か Windows 用に作成されたかどうか、任意のプログラムで使用できます。 ただし、これらは、アプリケーション フレームワークのドキュメント クラスを定義するデータ構造を実装するため最も役立ちます。 これらの特殊なコレクション クラスを派生させたり、またはテンプレート クラスに基づいてそれらを作成することができます。 これらの方法の詳細については、記事を参照してください。[コレクション](../mfc/collections.md)します。 テンプレートのコレクション クラスの一覧は、記事を参照してください。[配列、リスト、およびマップのテンプレート クラス](../mfc/template-classes-for-arrays-lists-and-maps.md)します。

配列は、連続してメモリに格納されている 1 次元のデータ構造です。 要素のインデックスの要素のサイズを乗算して結果を配列のベース アドレスに追加する任意の要素のメモリ アドレスを計算できるので非常に高速なランダム アクセスをサポートしています。 配列、配列全体が過去から配列に要素を挿入する場合は、挿入される要素が挿入される要素を確保するために移動する必要が非常に不経済です。 配列は、拡大し、必要に応じて圧縮できます。

リストは配列に似ていますが、まったく違う方法で格納されます。 リスト内の各要素には、ためダブルリンク リストの前または次の要素へのポインターも含まれています。 追加またはいくつかのヒントを変更する必要がありますのみ行うために項目を削除する非常に高速になります。 ただし、リストの検索できる高価なすべての検索は、リストの終了のいずれかで開始する必要があるためです。

マップは、キーの値をデータ値に関連します。 たとえば、マップのキーでは、文字列とデータの一覧へのポインターに可能性があります。 特定の文字列に関連付けられたポインターを提供する、マップに問い合わせることができます。 マップのキー参照ハッシュ テーブルを使用するためには、マップの検索は高速です。 追加して、アイテムの削除も高速です。 マップは、補助的なインデックスとして他のデータ構造によく使用されます。 MFC は、特殊なという名前のマップを使用して、[メッセージ マップ](../mfc/mapping-messages.md)Windows メッセージをそのメッセージ ハンドラー関数へのポインターにマップします。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

