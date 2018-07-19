---
title: 'アクティベーション: 動詞 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c484231eb87144a6546ff2b8b7061a5339820ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331075"
---
# <a name="activation-verbs"></a>アクティベーション : 動詞
この記事では、OLE のロールのプライマリとセカンダリの動詞プレイを説明します。[アクティベーション](../mfc/activation-cpp.md)です。  
  
 通常、埋め込みアイテムをダブルクリックすることができますを編集します。 ただし、特定の項目には、この方法は動作しません。 たとえば、サウンド レコーダー アプリケーションで作成された項目をダブルクリックするとはで開かれませんサーバーを別のウィンドウ代わりに、サウンドを再生します。  
  
 この動作の違いの理由は、サウンド レコーダー項目がある場合、異なる「プライマリ動詞です」 主動詞は、ユーザーが OLE 項目をダブルクリックしたときに実行されたアクションです。 ほとんどの種類の OLE 項目では、プライマリの動詞は、編集、アイテムを作成したサーバーを起動させるです。 サウンド レコーダー項目などの項目の種類によっては、プライマリの動詞は、再生がします。  
  
 OLE 項目の多くの種類は、1 つだけの動詞をサポートし、編集が、最も一般的なです。 ただし、項目の種類によっては、複数の動詞をサポートします。 たとえば、項目は、サポート、サウンド レコーダーは、セカンダリ動詞として編集します。  
  
 頻繁に使用されている他の動詞は Open です。 Open 動詞は、別のウィンドウで、サーバー アプリケーションを起動点を除いて編集と同じです。 コンテナー アプリケーションまたはサーバー アプリケーションのいずれかが、インプレース アクティブ化をサポートしていない場合、この動詞を使用する必要があります。  
  
 主動詞以外のすべての動詞は、項目を選択するとサブメニューのコマンドで呼び出す必要があります。 このサブメニュー項目によってサポートされるすべての動詞を含みが通常に達すると、 *typename* **オブジェクト**コマンドを**編集**メニュー。 詳細について、 *typename* **オブジェクト**コマンドは、「[メニューとリソース: コンテナーの変更点](../mfc/menus-and-resources-container-additions.md)です。  
  
 サーバー アプリケーションでサポートされる動作は、Windows レジストリ データベースに一覧表示されます。 Microsoft Foundation Class ライブラリで、サーバー アプリケーションが書き込まれた場合、サーバーが開始されたときにすべての動詞に自動的に登録されます。 それ以外の場合は、サーバー アプリケーションの初期化フェーズ中にそれらを登録する必要があります。 詳細については、記事を参照してください。[登録](../mfc/registration.md)です。  
  
## <a name="see-also"></a>関連項目  
 [アクティブ化](../mfc/activation-cpp.md)   
 [コンテナー](../mfc/containers.md)   
 [サーバー](../mfc/servers.md)

