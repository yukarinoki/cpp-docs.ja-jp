---
title: 'MFC ActiveX コントロール: オートメーション サーバーの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 617d84b8603467da74b21be8c2bfb2e6cb418f7b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346764"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX コントロール : オートメーション サーバーの作成
MFC ActiveX コントロールは、プログラムで別のアプリケーションでそのコントロールを埋め込むと、アプリケーションのコントロールのメソッドを呼び出すことを目的としてオートメーション サーバーとして開発できます。 このようなコントロールがまだできるように ActiveX コントロール コンテナーでホストされます。  
  
### <a name="to-create-a-control-as-an-automation-server"></a>オートメーション サーバーとしてコントロールを作成するには  
  
1.  [作成](../mfc/reference/mfc-activex-control-wizard.md)コントロール。  
  
2.  [メソッドを追加](../mfc/mfc-activex-controls-methods.md)です。  
  
3.  オーバーライド[オーバーライド](../mfc/reference/colecontrol-class.md#isinvokeallowed)です。 詳細については、サポート技術情報記事 Q146120 を参照してください。  
  
4.  コントロールをビルドします。  
  
### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>オートメーション サーバー内のメソッドにアクセスするには  
  
1.  たとえば、アプリケーションを作成、 [MFC exe](../mfc/reference/mfc-application-wizard.md)です。  
  
2.  先頭に、`InitInstance`関数を次の行を追加します。  
  
     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]  
  
3.  クラス ビューでは、プロジェクト ノードを右クリックして**typelib クラス追加**タイプ ライブラリをインポートします。  
  
     これでは、ファイル名拡張子 .h および .cpp ファイルをプロジェクトに追加します。  
  
4.  ヘッダー ファイルで、クラスの ActiveX コントロールの 1 つまたは複数のメソッドを呼び出すには、次の行を追加:`#include filename.h`ファイル名は、タイプ ライブラリをインポートしたときに作成されたヘッダー ファイルの名前を指定します。  
  
5.  関数では、ActiveX コントロールのメソッドに呼び出しを行ったが、コントロールのラッパー クラスのオブジェクトを作成するコードを追加し、ActiveX オブジェクトを作成します。 たとえば、次の MFC コードがインスタンス化、`CCirc`制御、キャプション プロパティを取得およびダイアログ ボックスで [ok] ボタンがクリックされたときに、結果が表示されます。  
  
     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]  
  
 アプリケーションで使用した後、ActiveX コントロールにメソッドを追加する場合は、タイプ ライブラリをインポートしたときに作成されたファイルを削除することによって、アプリケーションでコントロールの最新のバージョンを使用を開始できます。 再度、タイプ ライブラリをインポートします。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

