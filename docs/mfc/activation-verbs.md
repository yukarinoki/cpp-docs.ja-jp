---
description: '詳細については、「Activation: Verb」を参照してください。'
title: アクティベーション:動詞
ms.date: 11/04/2016
helpviewer_keywords:
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
ms.openlocfilehash: 2c680452d87f1fcfd1ee2a0b8362dbaab8c0affd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325933"
---
# <a name="activation-verbs"></a>アクティベーション:動詞

この記事では、OLE [アクティベーション](activation-cpp.md)でのプライマリ動詞とセカンダリ動詞の動作について説明します。

通常、埋め込み項目をダブルクリックすると、ユーザーが編集できるようになります。 ただし、特定の項目がこのように動作しません。 たとえば、サウンドレコーダーアプリケーションで作成された項目をダブルクリックしても、サーバーは別のウィンドウで開かれません。代わりに、サウンドを再生します。

この動作の違いは、サウンドレコーダーの項目の "主動詞" が異なるためです。 プライマリ動詞は、ユーザーが OLE 項目をダブルクリックしたときに実行されるアクションです。 ほとんどの種類の OLE アイテムでは、主な動詞は Edit で、アイテムを作成したサーバーを起動します。 サウンドレコーダー項目など、一部の種類の項目では、主動詞が再生されます。

OLE 項目の種類によってサポートされる動詞は1つだけであり、編集が最も一般的なものです。 ただし、一部の種類の項目では複数の動詞がサポートしています。 たとえば、サウンドレコーダー項目では、セカンダリ動詞として編集がサポートされています。

頻繁に使用される別の動詞が開かれています。 Open 動詞は編集と同じですが、サーバーアプリケーションが別のウィンドウで起動される点が異なります。 この動詞は、コンテナーアプリケーションまたはサーバーアプリケーションがインプレースアクティベーションをサポートしていない場合に使用する必要があります。

プライマリ動詞以外の動詞は、項目を選択したときにサブメニューコマンドを使用して呼び出す必要があります。 このサブメニューには、項目でサポートされているすべての動詞が含まれており、通常は [**編集**] メニューの [ *typename* **Object** ] コマンドによってアクセスされます。 *Typename* **オブジェクト** コマンドの詳細については、「[メニューとリソース: コンテナーの追加](menus-and-resources-container-additions.md)」を参照してください。

サーバーアプリケーションがサポートしている動詞は、Windows 登録データベースに記載されています。 サーバーアプリケーションに Microsoft Foundation Class ライブラリが記述されている場合は、サーバーの起動時にすべての動詞が自動的に登録されます。 それ以外の場合は、サーバーアプリケーションの初期化フェーズ中に登録する必要があります。 詳細については、「 [登録](registration.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アクティベーション](activation-cpp.md)<br/>
[Containers](containers.md)<br/>
[サーバー](servers.md)
