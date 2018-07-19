---
title: ドキュメント テンプレートとドキュメント/ビューの作成プロセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2d8308e69cf53db4be51f6ce742df41edaa89ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348092"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>ドキュメント テンプレートとドキュメント/ビューの作成手順
フレームワークを関連するビューとフレーム ウィンドウとドキュメントを作成する複雑なプロセスを管理するには、次の 2 つのドキュメント テンプレート クラスを使用して:[関数](../mfc/reference/csingledoctemplate-class.md)SDI アプリケーション用と[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) MDI アプリケーション用。 A`CSingleDocTemplate`を作成し、同時に 1 つの型の 1 つのドキュメントを保存できます。 A`CMultiDocTemplate`は 1 つの型の多くの開いているドキュメントの一覧を保持します。  
  
 一部のアプリケーションでは、複数のドキュメント タイプをサポートします。 たとえば、アプリケーションでは、テキスト ドキュメントとグラフィックスのドキュメントをサポート可能性があります。 このようなアプリケーションは、[ファイル] メニューで、新しいコマンドを選択すると、ダイアログ ボックスを開くには使用可能な新しいドキュメント型一覧を示します。 サポートされているドキュメントの種類ごとに、アプリケーションは、個別のドキュメント テンプレート オブジェクトを使用します。 次の図は、次の 2 つのドキュメントの種類をサポートし、いくつかの開いているドキュメントを表示する MDI アプリケーションの構成を示しています。  
  
 ![2 つのドキュメント型を持つ MDI アプリケーション](../mfc/media/vc387h1.gif "vc387h1")  
2 つのドキュメント タイプをサポートする MDI アプリケーション  
  
 ドキュメント テンプレートが作成され、アプリケーションのオブジェクトによって保持されます。 アプリケーションの中に実行される主なタスクのいずれかの`InitInstance`機能は、適切な種類の 1 つまたは複数のドキュメント テンプレートを作成します。 この機能については、「[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)です。 Application オブジェクトは、テンプレートのリストにそれぞれのドキュメント テンプレートへのポインターを格納し、ドキュメント テンプレートを追加するためのインターフェイスを提供します。  
  
 2 つ以上のドキュメント型をサポートする必要がある場合への余分な呼び出しを追加する必要があります[AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)各ドキュメントの種類。  
  
 ドキュメント テンプレートのアプリケーションの一覧における位置に基づく各ドキュメント テンプレートのアイコンが登録されます。 ドキュメント テンプレートの順序はへの呼び出しに追加された順序によって決まります`AddDocTemplate`です。 MFC には、アプリケーションの最初のアイコン リソースは、アプリケーションのアイコン、[次へ] のアイコン リソースがあると最初のドキュメント アイコンが想定しています。  
  
 たとえば、ドキュメント テンプレートは、3 番目のアプリケーション用に 3 つです。 インデックス 3 のアプリケーションで、アイコン リソースがある場合は、ドキュメント テンプレートのアイコンが使用されます。 それ以外の場合は、インデックス 0 にあるアイコンは、既定値として使用します。  
  
## <a name="see-also"></a>関連項目  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [ドキュメント テンプレートの作成](../mfc/document-template-creation.md)   
 [ドキュメント/ビューの作成](../mfc/document-view-creation.md)   
 [MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../mfc/creating-new-documents-windows-and-views.md)

