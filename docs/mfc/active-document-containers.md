---
title: Active ドキュメント コンテナー
ms.date: 11/19/2018
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
ms.openlocfilehash: e2005ffed592fa1de278e0f6339d94687a20fd06
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377394"
---
# <a name="active-document-containers"></a>Active ドキュメント コンテナー

Microsoft Office バインダーや Internet Explorer などのアクティブ ドキュメント コンテナを使用すると、1 つのフレーム内で異なるアプリケーションタイプの複数のドキュメントを操作できます (ドキュメントの種類ごとに複数のアプリケーション フレームを作成して使用する代わりに)。

MFC では、クラス内のアクティブ な`COleDocObjectItem`ドキュメント コンテナーの完全なサポートが提供されます。 MFC アプリケーション ウィザードを使用して、MFC アプリケーション ウィザードの [複合ドキュメント サポート] ページで **[Active ドキュメント コンテナー** ] チェック ボックスをオンにして、アクティブ**ドキュメント**コンテナーを作成できます。 詳細については、「 [Active ドキュメント コンテナ アプリケーションの作成](../mfc/creating-an-active-document-container-application.md)」を参照してください。

アクティブ ドキュメント コンテナーの詳細については、以下を参照してください。

- [コンテナの要件](#container_requirements)

- [ドキュメント サイト オブジェクト](#document_site_objects)

- [サイト オブジェクトの表示](#view_site_objects)

- [オブジェクトの構築](#frame_object)

- [[ヘルプ] メニューのマージ](../mfc/help-menu-merging.md)

- [プログラム印刷](../mfc/programmatic-printing.md)

- [コマンド ターゲット](../mfc/message-handling-and-command-targets.md)

## <a name="container-requirements"></a><a name="container_requirements"></a>コンテナの要件

アクティブ ドキュメント コンテナーでのアクティブ ドキュメントのサポートは、単なるインターフェイス実装以上の意味を持ちます。 コンテナーは、アクティブ ドキュメント自体でこれらの拡張インターフェイスを使用する方法も認識する必要があるアクティブ なドキュメント拡張機能にも同様です。

アクティブ ドキュメントを統合するアクティブ ドキュメント コンテナーは、次のことが必要です。

- インターフェイスを介してオブジェクト ストレージを`IPersistStorage`処理できる、つまり、アクティブな各ドキュメントに`IStorage`インスタンスを提供する必要があります。

- OLE ドキュメントの基本的な埋め込み機能をサポートし、実装`IOleClientSite`する "site" オブジェクト (ドキュメントごとに 1 つ、または`IAdviseSink`埋め込む) を必要とする。

- 埋め込みオブジェクトまたはアクティブ ドキュメントの埋め込み有効化をサポートします。 コンテナのサイト オブジェクトは実装`IOleInPlaceSite`する必要があり、コンテナのフレーム オブジェクトは`IOleInPlaceFrame`を提供する必要があります。

- コンテナーがドキュメントとやり取りする`IOleDocumentSite`メカニズムを実装することで、アクティブ ドキュメントの拡張機能をサポートします。 コンテナーは、必要に応じてアクティブ ドキュメント`IOleCommandTarget`インターフェイス`IContinueCallback`を実装し、印刷や保存などの簡単なコマンドを取得できます。

フレーム オブジェクト、ビュー オブジェクト、およびコンテナ オブジェクトは、オプションで`IOleCommandTarget`実装して、特定のコマンドのディスパッチをサポート[できます。](../mfc/message-handling-and-command-targets.md) また、プログラム[による印刷](../mfc/programmatic-printing.md)をサポートするために、`IPrint`必要`IContinueCallback`に応じてビュー オブジェクトとコンテナ オブジェクトを実装し、プログラムによる印刷をサポートすることもできます。

次の図は、コンテナーとそのコンポーネント (左) と、アクティブなドキュメントとビュー (右) との間の概念的な関係を示しています。 アクティブドキュメントは、ストレージとデータを管理し、ビューは、そのデータを表示するか、オプションで印刷します。 太字のインターフェイスは、アクティブなドキュメント参加に必要なインターフェイスです。太字と斜体はオプションです。 他のすべてのインターフェイスが必要です。

![アクティブ ドキュメント コンテナー インターフェイス](../mfc/media/vc37gj1.gif "アクティブ ドキュメント コンテナー インターフェイス")

1 つのビューのみをサポートするドキュメントは、単一の具象クラスにビューコンポーネントとドキュメントコンポーネント (対応するインタフェース) の両方を実装できます。 また、一度に 1 つのビューしかサポートできないコンテナー サイトは、ドキュメント サイトとビュー サイトを 1 つの具象サイト クラスに結合できます。 ただし、コンテナのフレームオブジェクトは別個のオブジェクトである必要があり、コンテナのドキュメントコンポーネントは、アーキテクチャの全体像を示すためにここに含まれているだけです。アクティブなドキュメントコンテインメントアーキテクチャの影響を受けません。

## <a name="document-site-objects"></a><a name="document_site_objects"></a>ドキュメント サイト オブジェクト

アクティブ ドキュメントコンテインメントアーキテクチャでは、ドキュメントサイトは、`IOleDocument`インターフェイスを追加した OLE ドキュメントのクライアント サイト オブジェクトと同じです。

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

ドキュメント サイトは、概念上、1 つ以上の "サイトの表示" オブジェクトのコンテナです。 各ビュー サイト オブジェクトは、ドキュメント サイトによって管理されるドキュメントの個々のビュー オブジェクトに関連付けられます。 コンテナーがドキュメント サイトごとに 1 つのビューしかサポートできない場合、コンテナーは、単一の具象クラスを使用してドキュメント サイトとビュー サイトを実装できます。

## <a name="view-site-objects"></a><a name="view_site_objects"></a>サイト オブジェクトの表示

コンテナのビュー サイト オブジェクトは、ドキュメントの特定のビューの表示領域を管理します。 標準`IOleInPlaceSite`インターフェイスをサポートするだけでなく、ビュー サイトは一般にプログラムによる`IContinueCallback`印刷制御を実装します。 (ビュー オブジェクトはクエリを実行`IContinueCallback`しないので、実際にコンテナが望むオブジェクトに実装できることに注意してください)。

複数のビューをサポートするコンテナーは、ドキュメント サイト内に複数のビュー サイト オブジェクトを作成できる必要があります。 これにより、各ビューに個別のアクティブ化サービスと非アクティブ化`IOleInPlaceSite`サービスが提供されます。

## <a name="frame-object"></a><a name="frame_object"></a>フレーム オブジェクト

コンテナのフレーム オブジェクトは、ほとんどの場合、OLE ドキュメントでのインプレース アクティブ化に使用されるフレームと同じフレーム、つまりメニューとツール バーのネゴシエーションを処理するフレームです。 ビュー オブジェクトは、 を介して`IOleInPlaceSite::GetWindowContext`この Frame オブジェクトにアクセスできます。

アクティブなドキュメント コンテナは、 を追加`IOleCommandTarget`してフレームを拡張できます。 これにより、アクティブ ドキュメントのユーザー インターフェイスから発信されたコマンドを、このインターフェイスで同じコマンド **([ファイル]** メニューの [新規作成]、[**開く**]、[**名前を付けて保存**]、[**印刷**] など) を送信できるようにするのと同じ方法で、このインターフェイスが受信できます。**コピー**、**貼り付け**、**元に戻す**、その他を編集する) をアクティブなドキュメントに編集します。 詳細については、「コマンド[ターゲット」を](../mfc/message-handling-and-command-targets.md)参照してください。

## <a name="see-also"></a>関連項目

[Active ドキュメント コンテインメント](../mfc/active-document-containment.md)
