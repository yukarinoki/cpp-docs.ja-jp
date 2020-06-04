---
title: 'コンテナー : 高度な機能'
ms.date: 11/04/2016
helpviewer_keywords:
- links [MFC], to embedded OLE objects
- containers [MFC], links to embedded OLE objects
- containers [MFC], advanced features
- container/server applications [MFC]
- embedded objects [MFC]
- OLE controls [MFC], containers
- OLE containers [MFC], advanced features
- server/container applications [MFC]
- containers [MFC], container applications
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
ms.openlocfilehash: cf130bf8dead5c59548821658b979785c4d54726
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376493"
---
# <a name="containers-advanced-features"></a>コンテナー : 高度な機能

この記事では、オプションの高度な機能を既存のコンテナー アプリケーションに組み込むために必要な手順について説明します。 これらの機能は次のとおりです。

- [コンテナとサーバーの両方であるアプリケーション](#_core_creating_a_container_server_application)

- [埋め込みオブジェクトへの OLE リンク](#_core_links_to_embedded_objects)

## <a name="creating-a-containerserver-application"></a><a name="_core_creating_a_container_server_application"></a>コンテナー/サーバー アプリケーションの作成

コンテナー/サーバー・アプリケーションは、コンテナーとサーバーの両方として機能するアプリケーションです。 この例は、Windows 用のマイクロソフトの Word です。 Word for Windows ドキュメントは他のアプリケーションに埋め込むことも、Word for Windows 文書にアイテムを埋め込むこともできます。 コンテナー アプリケーションをコンテナーと完全なサーバーの両方に変更するプロセス (組み合わせコンテナー/ミニサーバー アプリケーションを作成することはできません) は、サーバー全体を作成するプロセスと似ています。

「[サーバー: サーバーの実装」](../mfc/servers-implementing-a-server.md)には、サーバー アプリケーションの実装に必要なタスクが多数記載されています。 コンテナー・アプリケーションをコンテナー/サーバー・アプリケーションに変換する場合は、同じタスクのいくつかを実行して、コンテナーにコードを追加する必要があります。 次に、考慮すべき重要事項を示します。

- アプリケーション ウィザードで作成されたコンテナー コードは、既に OLE サブシステムを初期化しています。 そのサポートのために何かを変更または追加する必要はありません。

- ドキュメント クラスの基本クラスが 、`COleDocument`の場合は常に`COleServerDoc`、 に基底クラスを変更します。

- サーバー`COleClientItem::CanActivate`自体がインプレイス編集に使用されている間に、アイテムがインプレースで編集されないようにオーバーライドします。

   たとえば、MFC OLE サンプル[OCLIENT](../overview/visual-cpp-samples.md)には、コンテナー/サーバー アプリケーションによって作成されたアイテムが埋め込まれています。 OCLIENT アプリケーションを開き、コンテナー/サーバー アプリケーションによって作成されたアイテムをインプレース編集します。 アプリケーションのアイテムを編集する際に、MFC OLE サンプル[HIERSVR](../overview/visual-cpp-samples.md)で作成したアイテムを埋め込むことにしました。 これを行うには、インプレース アクティベーションを使用できません。 このアイテムを有効にするには、HIERSVR を完全に開く必要があります。 Microsoft Foundation クラス ライブラリではこの OLE 機能がサポート`COleClientItem::CanActivate`されていないため、オーバーライドすると、この状況をチェックして、アプリケーションで発生する可能性のある実行時エラーを防ぐことができます。

新しいアプリケーションを作成し、それをコンテナー/サーバー アプリケーションとして機能させる場合は、アプリケーション ウィザードの [OLE オプション] ダイアログ ボックスでそのオプションを選択すると、このサポートが自動的に作成されます。 詳細については、「概要 : [ActiveX コントロール コンテナーの作成](../mfc/reference/creating-an-mfc-activex-control-container.md)」を参照してください。 MFC サンプルの詳細については[、「MFC サンプル](../overview/visual-cpp-samples.md#mfc-samples)」を参照してください。

MDI アプリケーションをそれ自体に挿入することはできません。 コンテナ/サーバーであるアプリケーションは、SDI アプリケーションでない限り、それ自体に挿入できません。

## <a name="links-to-embedded-objects"></a><a name="_core_links_to_embedded_objects"></a>埋め込みオブジェクトへのリンク

埋め込みオブジェクトへのリンク機能を使用すると、ユーザーは、コンテナー アプリケーション内の埋め込みオブジェクトへの OLE リンクを含むドキュメントを作成できます。 たとえば、スプレッドシートが埋め込まれたワード プロセッサでドキュメントを作成します。 アプリケーションが埋め込みオブジェクトへのリンクをサポートしている場合、ワード プロセッサのドキュメントに含まれているスプレッドシートへのリンクを貼り付けることができます。 この機能により、アプリケーションは、ワードプロセッサが最初に取得した場所を知らなくても、スプレッドシートに含まれる情報を使用できます。

#### <a name="to-link-to-embedded-objects-in-your-application"></a>アプリケーション内の埋め込みオブジェクトにリンクするには

1. の代わりにから`COleLinkingDoc`ドキュメント クラス`COleDocument`を派生させます。

1. OLE 開発ツールに付属のクラス ID ジェネレータを使用して、アプリケーションの OLE クラス ID (**CLSID**) を作成します。

1. アプリケーションを OLE に登録します。

1. アプリケーション`COleTemplateServer`クラスのメンバーとしてオブジェクトを作成します。

1. アプリケーション クラスの`InitInstance`メンバー関数で、次の操作を行います。

   - オブジェクトの`COleTemplateServer``ConnectTemplate`メンバー関数を呼び出して、オブジェクトをドキュメント テンプレートに接続します。

   - メンバ関数`COleTemplateServer::RegisterAll`を呼び出して、すべてのクラス オブジェクトを OLE システムに登録します。

   - `COleTemplateServer::UpdateRegistry` を呼び出します。 アプリケーション`UpdateRegistry`が「/Embedded」スイッチで起動*されない場合は*、OAT_CONTAINERする必要がある唯一のパラメーターです。 これにより、埋め込みオブジェクトへのリンクをサポートできるコンテナーとしてアプリケーションが登録されます。

      アプリケーションが 「/Embedded」スイッチで起動された場合、サーバー アプリケーションと同様に、メイン ウィンドウを表示しないようにする必要があります。

MFC OLE サンプル[OCLIENT では](../overview/visual-cpp-samples.md)、この機能を実装しています。 これを行う方法の例については`InitInstance`*、OCLIENT の関数を参照してください。* このサンプル アプリケーションの CPP ファイル。

## <a name="see-also"></a>関連項目

[Containers](../mfc/containers.md)<br/>
[サーバー](../mfc/servers.md)
