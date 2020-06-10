---
title: Active ドキュメント コンテナー アプリケーションの作成
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
ms.openlocfilehash: 860a8531a96a0671c808dba13523b492026eafe0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616352"
---
# <a name="creating-an-active-document-container-application"></a>Active ドキュメント コンテナー アプリケーションの作成

Active ドキュメントコンテナーアプリケーションを作成する最も簡単かつ最も推奨される方法は、MFC アプリケーションウィザードを使用して MFC EXE コンテナーアプリケーションを作成し、次に、active document コンテインメントをサポートするようにアプリケーションを変更することです。

#### <a name="to-create-an-active-document-container-application"></a>Active ドキュメントコンテナーアプリケーションを作成するには

1. [**ファイル**] メニューの [**新規作成**] サブメニューから [**プロジェクト**] をクリックします。

1. 左側のウィンドウで、[ **Visual C++** プロジェクトの種類] をクリックします。

1. 右ペインで [ **MFC アプリケーション**] を選択します。

1. プロジェクトに*Myproj*という名前を指定し、[ **OK]** をクリックします。

1. [**複合ドキュメントのサポート**] ページを選択します。

1. **コンテナー**または**コンテナー/フルサーバー**オプションを選択します。

1. [ **Active ドキュメントコンテナー** ] チェックボックスをオンにします。

1. **[完了]** をクリックします。

1. MFC アプリケーションウィザードでアプリケーションの生成が完了したら、ソリューションエクスプローラーを使用して次のファイルを開きます。

   - *MyProjview .cpp*

1. *Myprojview .cpp*で、次の変更を行います。

   - で `CMyProjView::OnPreparePrinting` 、関数の内容を次のコードに置き換えます。

     [!code-cpp[NVC_MFCDocView#56](codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]

   `OnPreparePrinting`印刷サポートを提供します。 このコード `DoPreparePrinting` は、既定の印刷準備であるを置き換えます。

   Active ドキュメントコンテインメントでは、より優れた印刷スキームが提供されます。

   - 最初に、インターフェイスを使用してアクティブドキュメントを呼び出し、 `IPrint` それ自体を印刷するように指示できます。 これは以前の OLE コンテインメントとは異なり、コンテナーは、含まれている項目のイメージをプリンターオブジェクトにレンダリングする必要がありました `CDC` 。

   - 失敗した場合は、含まれている項目にインターフェイスを通じて出力するように指示します。 `IOleCommandTarget`

   - それでも失敗する場合は、アイテムを独自にレンダリングします。

   前のコードで実装された静的メンバー関数とは、 `COleDocObjectItem::OnPrint` `COleDocObjectItem::OnPreparePrinting` この改善された印刷スキームを処理します。

1. 独自のの実装を追加し、アプリケーションをビルドします。

## <a name="see-also"></a>関連項目

[Active ドキュメント コンテインメント](active-document-containment.md)
