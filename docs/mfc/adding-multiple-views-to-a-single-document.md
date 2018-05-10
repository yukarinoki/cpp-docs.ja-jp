---
title: 1 つのドキュメントへの複数のビューの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb40b356b5601e19c33083c7b731a1dc411de3c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="adding-multiple-views-to-a-single-document"></a>シングル ドキュメントへのマルチ ビューの追加
Microsoft Foundation Class (MFC) ライブラリで作成したシングル ドキュメント インターフェイス (SDI) アプリケーション、各ドキュメントの種類は、1 つのビューの種類に関連付けられています。 場合によってを新しいビューを持つドキュメントの現在のビューを切り替えることがあることをお勧めします。  
  
> [!TIP]
>  1 つのドキュメントに複数のビューを実装する追加手順については、次を参照してください。 [CDocument::AddView](../mfc/reference/cdocument-class.md#addview)と[収集](../visual-cpp-samples.md)MFC サンプルです。  
  
 この機能を実装するには、追加する新しい`CView`-派生クラスと既存の MFC アプリケーションを動的にビューを切り替えるためのコードを追加します。  
  
 手順は次のとおりです。  
  
-   [既存のアプリケーション クラスを変更します。](#vcconmodifyexistingapplicationa1)  
  
-   [作成および変更、新しいビュー クラス](#vcconnewviewclassa2)  
  
-   [作成し、新しいビューを添付](#vcconattachnewviewa3)  
  
-   [切り替え関数を実装します。](#vcconswitchingfunctiona4)  
  
-   [ビューの切り替えのサポートを追加します。](#vcconswitchingtheviewa5)  
  
 このトピックの残りの部分には、次の前提としています。  
  
-   名前、 `CWinApp`-派生オブジェクトが`CMyWinApp`、および`CMyWinApp`が宣言され、MYWINAPP で定義されています。H と MYWINAPP です。CPP です。  
  
-   `CNewView` 新しい名前を指定`CView`-派生オブジェクト、および`CNewView`が宣言され、NEWVIEW で定義されています。H と NEWVIEW です。CPP です。  
  
##  <a name="vcconmodifyexistingapplicationa1"></a> 既存のアプリケーション クラスを変更します。  
 ビューの間で切り替えるには、アプリケーション、ビュー、およびそれらを切り替えるにはメソッドを格納するためのメンバー変数を追加することで、アプリケーション クラスを変更する必要があります。  
  
 宣言を次のコードを追加`CMyWinApp`MYWINAPP にします。H:  
  
 [!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]  
  
 新しいメンバー変数、`m_pOldView`と`m_pNewView`、現在のビューと新しく作成された 1 つをポイントします。 新しいメソッド (`SwitchView`)、ユーザーが要求されたときに、ビューを切り替えます。 メソッドの本体はでは、このトピックの後半で説明[切り替え関数の実装](#vcconswitchingfunctiona4)です。  
  
 最後の変更はアプリケーション クラスには、Windows メッセージを定義する新しいヘッダー ファイルを含める必要があります (**WM_INITIALUPDATE**) 切り替え関数内で使用されます。  
  
 MYWINAPP の include セクションで、次の行を挿入します。CPP:  
  
 [!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]  
  
 変更を保存し、次の手順に進みます。  
  
##  <a name="vcconnewviewclassa2"></a> 作成および変更、新しいビュー クラス  
 新しいビュー クラスの作成が簡単に作成を使用して、**クラスの新しい**クラス ビューで使用できるコマンド。 このクラスの唯一の要件はから派生して`CView`です。 この新しいクラスをアプリケーションに追加します。 新しいクラスをプロジェクトに追加する方法の詳細については、次を参照してください。[クラスの追加](../ide/adding-a-class-visual-cpp.md)です。  
  
 クラスをプロジェクトに追加した後は、いくつかのビュー クラスのメンバーのアクセシビリティを変更する必要があります。  
  
 NEWVIEW を変更します。アクセス指定子を変更することによって H`protected`に**パブリック**コンス トラクターとデストラクターのです。 これにより、作成して、動的に破棄して表示される前に、ビューの外観を変更するクラス。  
  
 変更を保存し、次の手順に進みます。  
  
##  <a name="vcconattachnewviewa3"></a> 作成し、新しいビューを添付  
 作成して、新しいビューをアタッチ、変更する必要があります、`InitInstance`アプリケーション クラスの関数。 変更は、新しいビュー オブジェクトを初期化両方を作成する新しいコードを追加`m_pOldView`と`m_pNewView`2 つの既存のビュー オブジェクトを使用します。  
  
 内で、新しいビューが作成されるため、`InitInstance`関数の場合、アプリケーションの有効期間、新規および既存の両方のビューを保持します。 ただし、アプリケーションでは、新しいビューが動的に作成と同様の簡単さでした。  
  
 呼び出しの後にこのコードを挿入`ProcessShellCommand`:  
  
 [!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]  
  
 変更を保存し、次の手順に進みます。  
  
##  <a name="vcconswitchingfunctiona4"></a> 切り替え関数を実装します。  
 前の手順で作成され、新しいビュー オブジェクトを初期化するコードを追加します。 最後の主要な部分は、切り替えのメソッドを実装する`SwitchView`です。  
  
 アプリケーションの実装ファイルの最後にクラス (MYWINAPP です。CPP)、次のメソッド定義を追加します。  
  
 [!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]  
  
 変更を保存し、次の手順に進みます。  
  
##  <a name="vcconswitchingtheviewa5"></a> ビューの切り替えのサポートを追加します。  
 最後の手順を呼び出すコードを追加、`SwitchView`メソッドは、アプリケーションは、ビューに切り替える必要があるとします。 これは、いくつかの方法で行うことができます。 ユーザーを選択するための新しいメニュー項目を追加するか、または特定の条件が満たされたときに内部的には、ビューの切り替えでします。  
  
 新しいメニュー項目とコマンド ハンドラー関数を追加する方法については、次を参照してください。[コマンドとコントロール通知のハンドラー](../mfc/handlers-for-commands-and-control-notifications.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

