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
ms.openlocfilehash: 1ef4ed9865d3a88a6ff85f777984b856d03cc48e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616355"
---
# <a name="containers-advanced-features"></a>コンテナー : 高度な機能

この記事では、既存のコンテナーアプリケーションにオプションの高度な機能を組み込むために必要な手順について説明します。 これらの機能は次のとおりです。

- [コンテナーとサーバーの両方であるアプリケーション](#_core_creating_a_container_server_application)

- [埋め込みオブジェクトへの OLE リンク](#_core_links_to_embedded_objects)

## <a name="creating-a-containerserver-application"></a><a name="_core_creating_a_container_server_application"></a>コンテナー/サーバーアプリケーションの作成

コンテナー/サーバーアプリケーションは、コンテナーとサーバーの両方として機能するアプリケーションです。 この例として、Microsoft Word for Windows が挙げられます。 Windows ドキュメント用 Word を他のアプリケーションに埋め込むことができます。また、Windows ドキュメント用 Word に項目を埋め込むこともできます。 コンテナーアプリケーションをコンテナーと完全サーバーの両方に変更するプロセス (コンテナー/ミニサーバーアプリケーションを組み合わせて作成することはできません) は、完全なサーバーを作成するプロセスと似ています。

「サーバー [: サーバーの実装](servers-implementing-a-server.md)」では、サーバーアプリケーションを実装するために必要な多数のタスクを示します。 コンテナーアプリケーションをコンテナー/サーバーアプリケーションに変換する場合は、それらのタスクの一部を実行して、コンテナーにコードを追加する必要があります。 考慮する必要がある重要事項を次に示します。

- アプリケーションウィザードによって作成されたコンテナーコードは、OLE サブシステムを既に初期化しています。 そのサポートについては、変更や追加を行う必要はありません。

- ドキュメントクラスの基底クラスがどこにある `COleDocument` 場合でも、基底クラスをに変更し `COleServerDoc` ます。

- `COleClientItem::CanActivate`サーバー自体を編集するために使用されている間に、項目の編集を回避するには、をオーバーライドします。

   たとえば、MFC OLE サンプル[OCLIENT](../overview/visual-cpp-samples.md)には、コンテナー/サーバーアプリケーションによって作成された項目が埋め込まれています。 OCLIENT アプリケーションを開き、コンテナー/サーバーアプリケーションによって作成された項目をインプレース編集します。 アプリケーションの項目を編集するときに、MFC OLE サンプル[HIERSVR](../overview/visual-cpp-samples.md)によって作成された項目を埋め込むことを選択します。 これを行うには、インプレースライセンス認証を使用できません。 この項目をアクティブにするには、HIERSVR を完全に開く必要があります。 Microsoft Foundation Class ライブラリではこの OLE 機能がサポートされていないため、をオーバーライド `COleClientItem::CanActivate` すると、このような状況を確認し、アプリケーションで実行時エラーが発生しないようにすることができます。

新しいアプリケーションを作成し、コンテナー/サーバーアプリケーションとして機能させる場合は、アプリケーションウィザードの [OLE オプション] ダイアログボックスでこのオプションを選択すると、このサポートが自動的に作成されます。 詳細については、「[概要: ActiveX コントロールコンテナーの作成](reference/creating-an-mfc-activex-control-container.md)」を参照してください。 MFC サンプルの詳細については、「 [Mfc サンプル](../overview/visual-cpp-samples.md#mfc-samples)」を参照してください。

MDI アプリケーションをそれ自体に挿入することはできないことに注意してください。 コンテナーまたはサーバーであるアプリケーションは、SDI アプリケーションでなければ、それ自体に挿入することはできません。

## <a name="links-to-embedded-objects"></a><a name="_core_links_to_embedded_objects"></a>埋め込みオブジェクトへのリンク

埋め込みオブジェクトへのリンク機能を使用すると、ユーザーは、コンテナーアプリケーション内の埋め込みオブジェクトへの OLE リンクを使用してドキュメントを作成できます。 たとえば、埋め込みスプレッドシートを含むワードプロセッサでドキュメントを作成します。 アプリケーションが埋め込みオブジェクトへのリンクをサポートしている場合は、ワードプロセッサのドキュメントに含まれているスプレッドシートへのリンクを貼り付けることができます。 この機能を使用すると、アプリケーションは、最初に word プロセッサがそれを入手した場所を知らなくても、スプレッドシートに含まれている情報を使用できます。

#### <a name="to-link-to-embedded-objects-in-your-application"></a>アプリケーション内の埋め込みオブジェクトにリンクするには

1. ドキュメントクラスをの代わりにから派生させ `COleLinkingDoc` `COleDocument` ます。

1. OLE 開発ツールに含まれているクラス ID ジェネレーターを使用して、アプリケーションの OLE クラス ID (**CLSID**) を作成します。

1. OLE にアプリケーションを登録します。

1. `COleTemplateServer`アプリケーションクラスのメンバーとしてオブジェクトを作成します。

1. アプリケーションクラスの `InitInstance` メンバー関数で、次の操作を行います。

   - オブジェクト `COleTemplateServer` のメンバー関数を呼び出して、オブジェクトをドキュメントテンプレートに接続し `ConnectTemplate` ます。

   - メンバー関数を呼び出して、 `COleTemplateServer::RegisterAll` すべてのクラスオブジェクトを OLE システムに登録します。

   - `COleTemplateServer::UpdateRegistry` を呼び出します。 `UpdateRegistry`アプリケーションが "/Embedded" スイッチで起動されていない場合は、の唯一のパラメーターを*OAT_CONTAINER*する必要があります。 これにより、埋め込みオブジェクトへのリンクをサポートするコンテナーとしてアプリケーションが登録されます。

      アプリケーションが "/Embedded" スイッチを使用して起動された場合、サーバーアプリケーションと同様に、メインウィンドウは表示されません。

MFC OLE サンプル[OCLIENT](../overview/visual-cpp-samples.md)では、この機能が実装されています。 これを行う方法の例については、OCLIENT の関数を参照してください `InitInstance` *。* このサンプルアプリケーションの CPP ファイル。

## <a name="see-also"></a>関連項目

[Containers](containers.md)<br/>
[サーバー](servers.md)
