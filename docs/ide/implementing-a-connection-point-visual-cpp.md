---
title: コネクション ポイントの実装 (Visual C++) | Microsoft Docs
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33328348"
---
# <a name="implementing-a-connection-point-visual-c"></a>コネクション ポイントの実装 (Visual C++)
接続ポイントの実装ウィザードを使用してコネクション ポイントを実装するには、ATL COM アプリケーションとしてか、ATL サポートを含む MFC アプリケーションとしてプロジェクトを作成しておく必要があります。 ATL アプリケーションを作成するか、[ATL オブジェクトを MFC アプリケーションに追加して](../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC アプリケーションの ATL サポートを実装するには、[ATL プロジェクト ウィザード](../atl/reference/atl-project-wizard.md)を利用できます。  
  
> [!NOTE]
>  MFC プロジェクトのコネクション ポイントを実装する方法の詳細については、「[コネクション ポイント](../mfc/connection-points.md)」を参照してください。  
  
 プロジェクトを作成したら、コネクション ポイントを実装するためには、最初に ATL オブジェクトを追加する必要があります。 ATL プロジェクトにオブジェクトを追加するウィザードの一覧が必要であれば、[ATL プロジェクトにオブジェクトとコントロールを追加する](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)方法に関するページを参照してください。  
  
> [!NOTE]
>  このウィザードは、ATL ダイアログ、ATL Server で作成した XML Web サービス、パフォーマンス オブジェクト、パフォーマンス カウンターに対応していません。  
  
 接続可能なオブジェクト (ソース) は、その発信インターフェイスごとにコネクション ポイントを公開します。 各発信インターフェイスは、オブジェクト上のクライアント (シンク) によって実装できます。 詳細については、「[ATL コネクション ポイント](../atl/atl-connection-points.md)」を参照してください。  
  
### <a name="to-implement-a-connection-point"></a>コネクション ポイントを実装するには  
  
1.  クラス ビューで、ATL オブジェクトのクラス名を右クリックします。  
  
2.  ショートカット メニューの **[追加]** をクリックし、**[接続ポイントの追加]** をクリックして [[接続ポイントの実装ウィザード]](../ide/implement-connection-point-wizard.md) を表示します。  
  
3.  該当するタイプ ライブラリから実装するコネクション ポイント インターフェイスを選択し、**[完了]** をクリックします。  
  
4.  クラス ビューで、コネクション ポイントごとに作成されたプロキシ クラスを確認します。 クラスは CProxy*InterfaceName*\<T> のように表示されます。クラスは [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) から派生します。  
  
5.  コネクション ポイント クラスをダブルクリックすると、コネクション ポイントのクラスの定義が表示されます。  
  
    -   独自のプロジェクトのインターフェイスに対してコネクション ポイントを実装する場合、次の定義が表示されます。  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         ローカル インターフェイスを実装する場合、メソッドとプロパティがクラス本体に表示されます。  
  
    -   別のインターフェイスに対してコネクション ポイントを実行する場合、定義にはインターフェイスのメソッドが含まれます。それぞれ、先頭に `Fire_` が付きます。  
  
## <a name="see-also"></a>参照  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [オブジェクトへの接続ポイントの追加](../atl/adding-connection-points-to-an-object.md)