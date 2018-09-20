---
title: 'アクティベーション: 動詞 |Microsoft Docs'
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
ms.openlocfilehash: 63b21e4d7f40d87b35d2ea5650f86801294affaa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425718"
---
# <a name="activation-verbs"></a>アクティベーション : 動詞

この記事では、OLE でロールのプライマリとセカンダリの動詞の再生をについて説明します[アクティベーション](../mfc/activation-cpp.md)します。

通常は、埋め込みアイテムをダブルクリックすると、ユーザーを編集することができます。 ただし、特定の項目には、この方法は動作しません。 たとえば、サウンド レコーダー アプリケーションで作成された項目をダブルクリックはで開かれません、サーバーを別のウィンドウ代わりに、サウンドを再生します。

この動作の違いの理由は、サウンド レコーダーの項目がある、さまざまな「プライマリ動詞」 主動詞は、ユーザーが OLE 項目をダブルクリックしたときに実行されるアクションです。 OLE 項目のほとんどの種類は、プライマリの動詞には、編集、アイテムを作成したサーバーを起動するです。 サウンド レコーダーの項目などの項目の種類によっては、プライマリの動詞は、再生が。

OLE 項目の多くの種類が 1 つだけの動詞をサポートし、編集は、最も一般的な 1 つ。 ただし、項目の種類によっては、複数の動詞をサポートします。 たとえば、項目をサポートするサウンド レコーダーは、セカンダリ動詞として編集します。

頻繁に使用されるもう 1 つの動詞は、Open です。 Open 動詞は、別のウィンドウで、サーバー アプリケーションが起動される点を除いて編集と同じです。 コンテナーのアプリケーションまたはサーバー アプリケーションのいずれかが、インプレース アクティブ化をサポートしていない場合、この動詞を使用する必要があります。

項目が選択されているときに、サブメニューのコマンドで主動詞以外のすべての動詞を呼び出す必要があります。 このサブメニュー アイテムでサポートされているすべての動詞を格納してあり、通常は、 *typename* **オブジェクト**コマンドを**編集**メニュー。 については、 *typename* **オブジェクト**コマンドは、「[メニューとリソース: コンテナーの変更点](../mfc/menus-and-resources-container-additions.md)します。

サーバー アプリケーションでサポートされる動作は、Windows の登録データベースに一覧表示されます。 場合は、Microsoft Foundation Class ライブラリで、サーバー アプリケーションが書き込まれると、サーバーの起動時にすべての動詞を自動的に登録がされます。 それ以外の場合は、サーバー アプリケーションの初期化フェーズ中にそれらを登録する必要があります。 詳細については、この記事を参照してください。[登録](../mfc/registration.md)します。

## <a name="see-also"></a>関連項目

[アクティベーション](../mfc/activation-cpp.md)<br/>
[コンテナー](../mfc/containers.md)<br/>
[サーバー](../mfc/servers.md)

