---
title: アクティベーション (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34b6d6e9313092a8f9a0a11967c7c6a62ed15e15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="activation-c"></a>アクティベーション (C++)
この記事では、OLE アイテムのビジュアル編集でのライセンス認証の役割について説明します。 ユーザーには、コンテナー ドキュメント内の OLE 項目が埋め込まれる後、は、使用する必要があります。 これを行うには、ユーザーがそのアイテムをアクティブ化すると、項目をダブルクリックします。 ライセンス認証のための最も頻繁にアクティビティを編集します。 OLE アイテム、編集、起動されたときに、項目を作成するサーバー アプリケーションに属しているを反映するように変更するのには、現在のフレーム ウィンドウ内のメニューとツールバーが。 この動作は、既知のインプレース アクティブ化は、コンテナー ドキュメントのウィンドウを離れることがなく複合ドキュメントに埋め込まれたアイテムを編集できます。  
  
 別のウィンドウで埋め込み OLE アイテムを編集することもできます。 これは、コンテナーまたはサーバー アプリケーションは、インプレース アクティブ化をサポートしていない場合に発生します。 ここでは、ユーザーをダブルクリックすると、埋め込みアイテム、別のウィンドウで、サーバー アプリケーションを起動し、埋め込み項目が独自のドキュメントとして表示されます。 ユーザーは、このウィンドウで項目を編集します。 編集が完了したら、ユーザーはサーバー アプリケーションを終了し、コンテナー アプリケーションを返します。  
  
 代わりに、ユーザーが選択できる「未処理の編集」で、 **\<オブジェクト > を開く**コマンドを**編集**メニュー。 これにより、オブジェクトが別のウィンドウで開きます。  
  
> [!NOTE]
>  OLE の version 1 で標準的な動作が別のウィンドウに埋め込まれたアイテムを編集し、一部の OLE アプリケーションがこの編集スタイルのみをサポートします。  
  
 インプレース アクティブ化は、ドキュメントを作成するドキュメント中心のアプローチを昇格させます。 ユーザーとして処理できます複合ドキュメント、単一のエンティティでは、アプリケーション間で切り替えることがなく取り組んでです。 ただし、インプレース アクティブ化がリンクされた項目は、埋め込まれた項目に対してのみ使用します。 それらは、別のウィンドウで編集する必要があります。 リンクされた項目が別の場所に実際に格納されているためにです。 リンクされた項目の編集は行わ、つまり、データの実際のコンテキスト内でデータが格納されています。 データが別のドキュメントに属しているユーザーに通知を別のウィンドウでリンクされた項目を編集します。  
  
 MFC では、入れ子になった、インプレース アクティブ化をサポートしていません。 コンテナー/サーバー アプリケーションをビルドするかどうかと、そのコンテナー/サーバーが別のコンテナーと、インプレース アクティブ化に埋め込まれている、そのことはできません、インプレース内に埋め込まれたオブジェクトを有効にします。  
  
 ユーザーをダブルクリックすると、その埋め込みアイテムの処理は、項目に対して定義されている動詞によって異なります。 詳細については、次を参照してください。[アクティベーション: 動詞](../mfc/activation-verbs.md)です。  
  
## <a name="see-also"></a>関連項目  
 [OLE](../mfc/ole-in-mfc.md)   
 [コンテナー](../mfc/containers.md)   
 [サーバー](../mfc/servers.md)

