---
title: フォーム ビュー (MFC) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a717ca80d84b884014a2567228829ffd87c5178
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930301"
---
# <a name="form-views-mfc"></a>フォーム ビュー (MFC)
フォームを追加するには、MFC ライブラリを含むをサポートする任意の Visual C アプリケーションを[フォーム ベースのアプリケーション](../mfc/reference/creating-a-forms-based-mfc-application.md)(1 つのビュー クラスから派生して`CFormView`)。 フォームをサポートするために、アプリケーションを最初に作成しなかった場合、Visual C は新しいフォームを挿入するときにこのサポートを追加します。 SDI または MDI アプリケーションは、既定値を実装する[ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)を選択すると、**新規**コマンド (既定では、上、**ファイル**メニュー)、VisualC++ では、ユーザー使用可能なフォームからを選択するように求められます。  
  
 ユーザーが選択すると、SDI アプリケーションでは、**新規**コマンドでは、フォームの現在のインスタンスは引き続き実行が見つからない場合、選択されたフォームを使用してアプリケーションの新しいインスタンスを作成します。 MDI アプリケーションでは、フォームの現在のインスタンスは、ユーザーが選択したときに実行が続行されます、**新規**コマンド。  
  
> [!NOTE]
>  フォームをダイアログ ベースのアプリケーションに挿入することができます (ダイアログ クラスがに基づいて 1 つずつ`CDialog`と 1 つのクラスの実装にも)。 ただし、ドキュメント/ビュー アーキテクチャを備えていない Visual C は自動的に実装しません、**ファイル**&#124;**新規**機能します。 さまざまなプロパティ ページ で、タブ付きダイアログ ボックスを実装することによって、その他のフォームを表示するのには、ユーザーの方法を作成する必要があります。  
  
 アプリケーションに新しいフォームを挿入するときに Visual C は、次を行います。  
  
-   選択したフォーム スタイル クラスのいずれかのクラスを作成します (`CFormView`、 `CRecordView`、 `CDaoRecordView`、または`CDialog`)。  
  
-   適切なスタイルを使用して、ダイアログ リソースを作成します (または、まだクラスに関連付けられていない既存のダイアログ リソースを使用することができます)。  
  
     既存のダイアログ リソースを選択した場合は、ダイアログ ボックスのプロパティ ページを使用してこれらのスタイルを設定する必要があります。 ダイアログ ボックスのスタイルを含める必要があります。  
  
     **WS_CHILD**= On  
  
     **WS_BORDER**= Off  
  
     **WS_VISIBLE**= Off  
  
     **WS_CAPTION =** オフ  
  
 ドキュメント/ビュー アーキテクチャに基づくアプリケーションの**新しいフォーム**コマンド (クラス ビューで右クリックして) も。  
  
-   作成、 `CDocument`-クラス  
  
     新しいクラスを作成するのではなく既存のすべてを使用できる`CDocument`-プロジェクト内のクラスをベースです。  
  
-   ドキュメント テンプレートが生成されます (から派生した`CDocument`) 文字列、メニューのおよびアイコンのリソースとします。  
  
     テンプレートを基になる新しいクラスを作成することもできます。  
  
-   呼び出しを追加`AddDocumentTemplate`アプリケーションの`InitInstance`コード。  
  
     Visual C は、各新しいフォームを作成すると、ユーザーが選択したときに、使用可能なフォームの一覧に、フォームを追加するには、このコードを追加、**新規**コマンド。 このコードには、フォームの関連するリソース ID と関連付けられているドキュメント、ビュー、および新しいフォーム オブジェクトを構成するフレーム クラスの名前が含まれています。  
  
     ドキュメント テンプレートは、ドキュメント、フレーム ウィンドウとビューの間の接続として機能します。 1 つのドキュメントには、多くのテンプレートを作成できます。  
  
 詳細については次を参照してください:  
  
-   [フォーム ベースのアプリケーションを作成します。](../mfc/reference/creating-a-forms-based-mfc-application.md)  
  
-   [プロジェクトへのフォームの挿入](../mfc/inserting-a-form-into-a-project.md)  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
