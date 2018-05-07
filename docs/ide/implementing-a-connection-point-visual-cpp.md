---
title: 接続ポイント (Visual C) を実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b75bf145da401ad9889353a1e65448831c602c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-a-connection-point-visual-c"></a>コネクション ポイントの実装 (Visual C++)
接続ポイントの実装ウィザードを使用した接続ポイントを実装するには、ATL COM アプリケーションまたは ATL サポートを含む MFC アプリケーションとしてにプロジェクトを作成が必要があります。 使用することができます、 [ATL プロジェクト ウィザード](../atl/reference/atl-project-wizard.md)ATL アプリケーションを作成するか、 [ATL オブジェクトを MFC アプリケーションに追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)MFC アプリケーションに対する ATL のサポートを実装します。  
  
> [!NOTE]
>  MFC プロジェクトの接続ポイントを実装する方法の詳細については、次を参照してください。[コネクション ポイント](../mfc/connection-points.md)です。  
  
 接続ポイントを実装する、プロジェクトを作成した後は、まず ATL オブジェクトを追加する必要があります。 参照してください[を追加するオブジェクトと ATL プロジェクトへのコントロールの](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)ATL プロジェクトにオブジェクトを追加するウィザードの一覧についてはします。  
  
> [!NOTE]
>  ウィザードでは、ATL ダイアログ、ATL サーバー、パフォーマンス オブジェクト、またはパフォーマンス カウンターで作成された XML Web サービスはサポートされていません。  
  
 接続可能なオブジェクト (ソース) は、その発信インターフェイスの各接続ポイントを公開できます。 オブジェクト (つまり、シンク) 上のクライアントでは、各発信インターフェイスを実装できます。 詳細については、次を参照してください。 [ATL コネクション ポイント](../atl/atl-connection-points.md)です。  
  
### <a name="to-implement-a-connection-point"></a>接続ポイントを実装するには  
  
1.  クラス ビューでは、ATL オブジェクトのクラス名を右クリックします。  
  
2.  をクリックして**追加**クリックしてショートカット メニューから**接続ポイントの追加**を表示する、[接続ポイントの実装ウィザード](../ide/implement-connection-point-wizard.md)です。  
  
3.  該当するタイプ ライブラリから実装し、をクリックするインターフェイスを接続ポイント選択**完了**です。  
  
4.  クラス ビューでは、接続ポイントごとに作成されたプロキシ クラスを確認します。 CProxy としてクラスが表示される*InterfaceName*\<T > から派生した[IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)です。  
  
5.  コネクション ポイントのクラスの定義を表示する接続ポイント クラスをダブルクリックします。  
  
    -   接続ポイントを独自のプロジェクトのインターフェイスを実装する場合、次の定義が表示されます。  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         ローカルのインターフェイスを実装するメソッドとプロパティがクラス本体に表示されます。  
  
    -   定義には、インターフェイスのメソッドが含まれています。 接続ポイントを別のインターフェイスを実装する場合は、先頭`Fire_`です。  
  
## <a name="see-also"></a>関連項目  
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [オブジェクトへの接続ポイントの追加](../atl/adding-connection-points-to-an-object.md)