---
description: '詳細情報: Active ドキュメントコンテナー'
title: Active ドキュメント コンテナー
ms.date: 11/19/2018
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
ms.openlocfilehash: 31cf2739595cb7a48b152dcefb6c21970b95f8bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150411"
---
# <a name="active-document-containers"></a>Active ドキュメント コンテナー

Microsoft Office バインダーや Internet Explorer などのアクティブなドキュメントコンテナーを使用すると、1つのフレーム内でさまざまな種類のアプリケーションの複数のドキュメントを操作できます (ドキュメントの種類ごとに複数のアプリケーションフレームを作成して使用する必要はありません)。

MFC では、クラスの active ドキュメントコンテナーを完全にサポート `COleDocObjectItem` しています。 Mfc アプリケーションウィザードの [**複合ドキュメントのサポート**] ページで [**アクティブドキュメントコンテナー** ] チェックボックスをオンにすると、active ドキュメントコンテナーを作成できます。 詳細については、「 [Active ドキュメントコンテナーアプリケーションの作成](creating-an-active-document-container-application.md)」を参照してください。

Active ドキュメントコンテナーの詳細については、以下を参照してください。

- [コンテナーの要件](#container_requirements)

- [ドキュメントサイトオブジェクト](#document_site_objects)

- [サイトオブジェクトの表示](#view_site_objects)

- [オブジェクトの構築](#frame_object)

- [[ヘルプ] メニューのマージ](help-menu-merging.md)

- [プログラムによる印刷](programmatic-printing.md)

- [コマンドターゲット](message-handling-and-command-targets.md)

## <a name="container-requirements"></a><a name="container_requirements"></a> コンテナーの要件

アクティブドキュメントコンテナーでのアクティブドキュメントのサポートは、インターフェイスの実装だけではありません。含まれているオブジェクトのインターフェイスの使用に関する知識も必要です。 これは active ドキュメントの拡張機能にも当てはまります。コンテナーは、アクティブなドキュメント自体でこれらの拡張インターフェイスを使用する方法についても理解している必要があります。

アクティブなドキュメントを統合する active ドキュメントコンテナーは、次のものが必要です。

- インターフェイスを介してオブジェクトストレージを処理できること `IPersistStorage` 。つまり、 `IStorage` 各アクティブドキュメントにインスタンスを提供する必要があります。

- とを実装する OLE ドキュメントの基本的な埋め込み機能をサポートしています (ドキュメントごとまたは埋め込みごとに1つ) `IOleClientSite` `IAdviseSink` 。

- 埋め込みオブジェクトまたはアクティブなドキュメントのインプレースアクティブ化をサポートします。 コンテナーのサイトオブジェクトはを実装する必要があり、 `IOleInPlaceSite` コンテナーの frame オブジェクトはを提供する必要があり `IOleInPlaceFrame` ます。

- を実装して、 `IOleDocumentSite` ドキュメントと対話するための機構を提供することで、アクティブドキュメントの拡張機能をサポートします。 コンテナーは、必要に応じて、アクティブドキュメントインターフェイス `IOleCommandTarget` を実装し、 `IContinueCallback` 印刷や保存などの簡単なコマンドを選択できます。

コマンドターゲットで説明されているように、フレームオブジェクト、ビューオブジェクト、およびコンテナーオブジェクトは、必要 `IOleCommandTarget` に応じて[](message-handling-and-command-targets.md)を実装して特定のコマンドのディスパッチをサポートできます。 また、ビューおよびコンテナーオブジェクトは、プログラムによる印刷 `IPrint` に関する説明に従って、およびを実装し `IContinueCallback` て、プログラムによる印刷をサポートする[](programmatic-printing.md)こともできます。

次の図は、コンテナーとそのコンポーネント (左側) と、アクティブなドキュメントとそのビュー (右側) との概念上の関係を示しています。 アクティブなドキュメントでは、ストレージとデータを管理し、そのデータを表示または必要に応じて印刷します。 太字のインターフェイスは、アクティブなドキュメントの参加に必要なインターフェイスです。太字と斜体は省略可能です。 その他のすべてのインターフェイスが必要です。

![アクティブ ドキュメント コンテナー インターフェイス](../mfc/media/vc37gj1.gif "アクティブ ドキュメント コンテナー インターフェイス")

1つのビューのみをサポートするドキュメントでは、ビューコンポーネントとドキュメントコンポーネント (つまり、対応するインターフェイス) の両方を1つの具象クラスに実装できます。 また、一度に1つのビューのみをサポートするコンテナーサイトでは、ドキュメントサイトとビューサイトを1つの具象サイトクラスにまとめることができます。 ただし、コンテナーのフレームオブジェクトは個別に維持する必要があり、コンテナーのドキュメントコンポーネントは、アーキテクチャの全体像を示すためにここにのみ含まれています。これは、アクティブなドキュメントコンテインメントアーキテクチャの影響を受けません。

## <a name="document-site-objects"></a><a name="document_site_objects"></a> ドキュメントサイトオブジェクト

Active ドキュメントコンテインメントアーキテクチャでは、ドキュメントサイトは、インターフェイスを追加した OLE ドキュメント内のクライアントサイトオブジェクトと同じです `IOleDocument` 。

```cpp
interface IOleDocumentSite : IUnknown
{
    HRESULT ActivateMe(IOleDocumentView *pViewToActivate);
}
```

ドキュメントサイトは、概念的には、1つまたは複数の "ビューサイト" オブジェクトのコンテナーです。 各ビューサイトオブジェクトは、ドキュメントサイトによって管理されるドキュメントの個々のビューオブジェクトに関連付けられています。 コンテナーがドキュメントサイトごとに1つのビューのみをサポートしている場合は、ドキュメントサイトとビューサイトを1つの具象クラスで実装できます。

## <a name="view-site-objects"></a><a name="view_site_objects"></a> サイトオブジェクトの表示

コンテナーのビューサイトオブジェクトは、ドキュメントの特定のビューの表示領域を管理します。 標準インターフェイスをサポートするだけでなく `IOleInPlaceSite` 、一般に、ビューサイト `IContinueCallback` はプログラムによる印刷コントロールのためにも実装します。 (View オブジェクトはに対してクエリを `IContinueCallback` 実行しないため、コンテナーが希望する任意のオブジェクトに実際に実装できます)。

複数のビューをサポートするコンテナーは、ドキュメントサイト内に複数のビューサイトオブジェクトを作成できる必要があります。 これにより、によって提供される個別のアクティベーションサービスと非アクティブ化サービスが各ビューに提供され `IOleInPlaceSite` ます。

## <a name="frame-object"></a><a name="frame_object"></a> Frame オブジェクト

コンテナーのフレームオブジェクトは、ほとんどの場合、OLE ドキュメントでのインプレースアクティブ化、つまりメニューとツールバーのネゴシエーションに使用されるフレームと同じフレームです。 ビューオブジェクトは、を介してこのフレームオブジェクトにアクセスできます。これにより `IOleInPlaceSite::GetWindowContext` 、コンテナードキュメントを表すコンテナーオブジェクト (ペインレベルのツールバーのネゴシエーションと含まれるオブジェクトの列挙を処理できます) にアクセスできるようになります。

アクティブドキュメントコンテナーは、を追加することでフレームを拡張でき `IOleCommandTarget` ます。 これにより、コンテナーが同じコマンド ( **File New**、 **Open**、 **Save as**、 **Print** など) を送信できるようにするのと同じ方法で、アクティブドキュメントのユーザーインターフェイスで生成されたコマンドを受け取ることができます。 **コピー**、 **貼り付け**、 **元に戻す** など) をアクティブなドキュメントに編集します。 詳細については、「 [コマンドターゲット](message-handling-and-command-targets.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Active ドキュメントコンテインメント](active-document-containment.md)
