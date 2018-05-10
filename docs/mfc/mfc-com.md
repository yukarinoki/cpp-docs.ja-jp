---
title: MFC COM |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MFC COM (MFC)
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8257631e46a1ebcf5c882d9f87c628c04ccc84f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-com"></a>MFC COM
最もアクティブ テンプレート ライブラリ (ATL) のように設計された COM をサポートする MFC のサブセットに設計された COM プログラミング用です。 このトピックのセクションには、COM の MFC のサポートがについて説明します  
  
 Active テクノロジ (など、ActiveX コントロール、Active ドキュメント コンテインメント、OLE、およびなど) が使用する言語に関係なく、ネットワーク環境内で相互に対話するのにソフトウェア コンポーネントを有効にするのにコンポーネント オブジェクト モデル (COM) を使用します。作成されます。 Active テクノロジは、デスクトップまたはインターネット上で実行されるアプリケーションの作成に使用できます。 詳細については、次を参照してください。 [COM の概要](../atl/introduction-to-com.md)または[、コンポーネント オブジェクト モデル](http://msdn.microsoft.com/library/windows/desktop/ms694363)です。  
  
 アクティブな技術には、次を含む、クライアントとサーバーの両方のテクノロジがあります。  
  
-   [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)、MFC バージョン 4.2 ではサポートでき、後でユーザーを表示する[アクティブ ドキュメント](../mfc/active-documents.md)(Microsoft Excel または Word ファイルなど) と、ドキュメントのネイティブ インターフェイス全体をアクティブ化クライアント領域全体のアプリケーション、 [active ドキュメント コンテナー](../mfc/active-document-containers.md) Office バインダーや Microsoft Internet Explorer などです。 によって提供されるドキュメントはときに、コンテナーが、クライアントとして動作[active ドキュメント サーバー](../mfc/active-document-servers.md)です。 インターネット アプリケーションでアクティブなドキュメントの使い方の詳細についてを参照してください: [、インターネット上の Active ドキュメント](../mfc/active-documents-on-the-internet.md)です。  
  
-   ActiveX コントロールは、Web サイトなどのコンテナーで使用できる対話型のオブジェクトです。 ActiveX コントロールの詳細についてを参照してください。  
  
    -   [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)  
  
    -   [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)  
  
    -   [概要: インターネット](../mfc/mfc-internet-programming-basics.md)  
  
    -   [インターネットで使用する既存の ActiveX コントロールのアップグレードします。](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [ActiveX コントロールのデバッグ](/visualstudio/debugger/how-to-debug-an-activex-control)  
  
-   アクティブ スクリプト ブラウザーまたはサーバーから 1 つ以上の ActiveX コントロールの統合の動作を制御します。 アクティブ スクリプトの詳細については、次を参照してください。 [、インターネット上の Active テクノロジ](../mfc/active-technology-on-the-internet.md)です。  
  
-   [オートメーション](../mfc/automation.md)(以前の OLE オートメーション) 1 つのアプリケーションを別のアプリケーションで実装されているオブジェクトを操作する、または""のオブジェクトを公開操作できるようにできるようになります。  
  
     自動オブジェクトは、ローカルまたは別のコンピューターにネットワーク経由でアクセス可能) リモートにあります。 OLE オブジェクトと COM オブジェクトは、どちらもオートメーションを利用できます。  
  
-   このセクションでの例については、MFC を使用して COM コンポーネントを記述する方法について情報を提供するも[コネクション ポイント](../mfc/connection-points.md)です。  
  
 Active テクノロジを今すぐと呼ばれるものではなく OLE と呼ばれる引き続きの詳細については、トピックを参照してください。 [OLE](../mfc/ole-in-mfc.md)です。  
  
 また、サポート技術情報の記事 Q248019 を参照してください: HOWTO: ようにサーバー ビジー状態 ダイアログ ボックスから表示中に、時間のかかる COM 操作します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)  
  
 [オートメーション](../mfc/automation.md)  
  
 [接続ポイント](../mfc/connection-points.md)  
  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)

