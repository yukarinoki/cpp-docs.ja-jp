---
title: ドキュメントテンプレートとドキュメントビューの作成プロセス
ms.date: 11/19/2018
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
ms.openlocfilehash: b96a11926927e89890ca268dcff7d347079b25fb
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615778"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>ドキュメント テンプレートとドキュメント/ビューの作成手順

関連するビューとフレームウィンドウでドキュメントを作成する複雑なプロセスを管理するために、フレームワークでは2つのドキュメントテンプレートクラスを使用します。 SDI アプリケーションの場合は[CSingleDocTemplate](reference/csingledoctemplate-class.md) 、MDI アプリケーションの場合は[CMultiDocTemplate](reference/cmultidoctemplate-class.md)です。 は、一度に1つ `CSingleDocTemplate` の種類のドキュメントを作成して保存できます。 は、 `CMultiDocTemplate` 1 つの種類の開いているドキュメントの一覧を保持します。

アプリケーションによっては、複数の種類のドキュメントをサポートしています。 たとえば、アプリケーションでテキストドキュメントやグラフィックスドキュメントをサポートする場合があります。 このようなアプリケーションでは、ユーザーが [ファイル] メニューの [新規作成] を選択すると、ダイアログボックスに、開くことのできる新しいドキュメントの種類の一覧が表示されます。 サポートされているドキュメントの種類ごとに、アプリケーションは個別のドキュメントテンプレートオブジェクトを使用します。 次の図は、2種類のドキュメントをサポートし、いくつかの開いているドキュメントを表示する MDI アプリケーションの構成を示しています。

![2 ドキュメント タイプを持つ MDI アプリケーション](../mfc/media/vc387h1.gif "2 ドキュメント タイプを持つ MDI アプリケーション") <br/>
2 つのドキュメント タイプをサポートする MDI アプリケーション

ドキュメントテンプレートは、アプリケーションオブジェクトによって作成および管理されます。 アプリケーションの機能中に実行される主なタスクの1つは `InitInstance` 、適切な種類の1つ以上のドキュメントテンプレートを作成することです。 この機能については、[ドキュメントテンプレートの作成](document-template-creation.md)に関するページを参照してください。 アプリケーションオブジェクトは、テンプレートの一覧に各ドキュメントテンプレートへのポインターを格納し、ドキュメントテンプレートを追加するためのインターフェイスを提供します。

2つ以上のドキュメントの種類をサポートする必要がある場合は、ドキュメントの種類ごとに[、adddoctemplate](reference/cwinapp-class.md#adddoctemplate)の呼び出しを追加する必要があります。

アプリケーションのドキュメントテンプレートの一覧での位置に基づいて、各ドキュメントテンプレートに対してアイコンが登録されます。 ドキュメントテンプレートの順序は、の呼び出しによって追加された順序によって決まり `AddDocTemplate` ます。 MFC では、アプリケーションの最初のアイコンリソースがアプリケーションアイコンであり、次のアイコンリソースが最初のドキュメントアイコンであることを前提としています。

たとえば、ドキュメントテンプレートはアプリケーションの3番目のテンプレートです。 インデックス3のアプリケーションにアイコンリソースがある場合、そのアイコンがドキュメントテンプレートに使用されます。 それ以外の場合は、インデックス0のアイコンが既定値として使用されます。

## <a name="see-also"></a>関連項目

[MFC の一般的なトピック](general-mfc-topics.md)<br/>
[ドキュメント テンプレートの作成](document-template-creation.md)<br/>
[ドキュメントおよびビューの作成](document-view-creation.md)<br/>
[MFC オブジェクト間の関係](relationships-among-mfc-objects.md)<br/>
[新しいドキュメント、ウィンドウ、およびビューの作成](creating-new-documents-windows-and-views.md)
