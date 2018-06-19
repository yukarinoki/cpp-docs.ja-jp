---
title: 配列、リスト、およびマップ クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 41dfe0b36548d87b5e0501c557e70f3cf11eea5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345294"
---
# <a name="array-list-and-map-classes"></a>配列、リスト、マップ クラス
コレクション クラスのグループを提供するクラス ライブラリのデータの集計を処理するため、配列、リスト、およびマップ — さまざまなオブジェクトおよび定義済みの型を保持することができます。 コレクションのサイズは動的にします。 これらのクラスは、か Windows 用に記述するかどうか、任意のプログラムで使用できます。 ただし、これらは、アプリケーション フレームワークのドキュメント クラスを定義するデータ構造を実装するため最も役立ちます。 すぐに、これらの特殊なコレクション クラスを派生できます。 またはテンプレート クラスに基づいて作成することができます。 これらの方法の詳細については、記事を参照してください。[コレクション](../mfc/collections.md)です。 テンプレートのコレクション クラスの一覧は、記事を参照してください。[配列、リスト、およびマップのテンプレート クラス.](../mfc/template-classes-for-arrays-lists-and-maps.md)です。  
  
 配列は、連続してメモリに格納されている 1 次元のデータ構造です。 要素のインデックスの要素のサイズを乗算し、配列のベース アドレスに結果を追加することによって任意の要素のメモリ アドレスを計算できるので非常に高速なランダム アクセスをサポートしています。 配列は配列全体が過去から挿入される要素が、挿入される要素を確保するために移動するが、配列に要素を挿入する必要が非常に不経済です。 配列では、拡張でき、必要に応じて縮小することができます。  
  
 リストでは、配列に似ていますが、まったく違う方法で格納されます。 一覧内の各要素には、ダブルリンク リストを作成の前または次の要素へのポインターも含まれています。 これは、追加や削除、いくつかのポインターの変更が行われるのみそうために非常に高速です。 ただし、リストの検索できる高価なすべての検索は、リストの終端のいずれかで開始する必要があるためです。  
  
 マップは、キーの値をデータ値に関連します。 たとえば、マップのキーでは、文字列とデータ一覧へのポインターを指定できます。 特定の文字列に関連付けられているポインターを与えるへのマップに問い合わせることができます。 マップの検索はマップ キー参照にハッシュ テーブルを使用するために高速です。 追加して、アイテムの削除も高速です。 マップは、補助のインデックスとして他のデータ構造によく使用されます。 MFC が特殊なという名前のマップを使用して、[メッセージ マップ](../mfc/mapping-messages.md)にそのメッセージのハンドラー関数へのポインターに Windows メッセージをマップします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

