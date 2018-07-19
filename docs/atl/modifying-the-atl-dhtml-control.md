---
title: ATL DHTML コントロールの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3810236aca4661a6cdcd8399294cdb73e97948fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356496"
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML コントロールの変更
ATL コントロール ウィザードは、ビルドして、コントロールを実行できるようにし、プロジェクト ファイル内のメソッドを記述する方法とディスパッチ方法を使用して、コントロールの C++ コードを DHTML を呼び出す方法を確認できるように、スタート コードを提供します。 インターフェイスにディスパッチ メソッドを追加することができます。 次に、HTML リソースのメソッドを呼び出すことができます。  
  
#### <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML コントロールを変更するには  
  
1.  クラス ビューでは、コントロール プロジェクトを展開します。  
  
     "UI"で終わるインターフェイスが 1 つのメソッドを持つことに注意してください`OnClick`です。 "UI"で終わらないインターフェイスには、すべてのメソッドはありません。  
  
2.  というメソッドを追加`MethodInvoked`"UI"で終わらないインターフェイス  
  
     このメソッドは、コントロール コンテナーで DHTML コントロールとの対話に使用されるインターフェイスが、コンテナーとの対話のために使用するインターフェイスに追加されます。 コンテナーのみでは、このメソッドを呼び出すことができます。  
  
3.  .Cpp ファイルでスタブ メソッドを検索し、たとえば、メッセージ ボックスを表示するコードを追加します。  
  
 [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  という別のメソッドを追加`HelloHTML`、この時点のみ"UI"で終了するインターフェイスに追加 検索、スタブ`HelloHTML`.cpp でメソッド ファイルし、たとえば、メッセージ ボックスを表示するコードを追加します。  
  
 [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  3 番目のメソッドを追加`GoToURL`、"UI"で終わらないインターフェイス このメソッドを呼び出すことによって実装[IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx)、次のようにします。  
  
 [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]  
  
     使用することができます、 **IWebBrowser2**メソッド ATL の .h ファイルでそのインターフェイスへのポインターを提供するためです。  
  
 次に、作成したメソッドを呼び出す HTML リソースを変更します。 これらのメソッドを呼び出すための 3 つのボタンを追加します。  
  
#### <a name="to-modify-the-html-resource"></a>HTML リソースを変更するには  
  
1.  ソリューション エクスプ ローラーでは、HTML リソースを表示する .htm ファイルをダブルクリックします。  
  
     HTML、特に、外部の Windows ディスパッチ メソッドの呼び出しを確認します。 HTML を呼び出す、プロジェクトの`OnClick`メソッド、およびパラメーターは、コントロールの本文を示します (`theBody`)、および色を割り当てる ("`red`")。 メソッドの呼び出しに続くテキストは、ボタンに表示されるラベルです。  
  
2.  もう 1 つ追加`OnClick`メソッド、色の変更のみです。 例えば:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
 ```  
  
     このメソッドは、ラベル付けされるボタンを作成**更新**制御を戻し、元、白の背景にユーザーがクリックすることです。  
  
3.  呼び出しを追加、`HelloHTML`メソッドを作成します。 例えば:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
 ```  
  
     このメソッドは、ラベル付けされるボタンを作成**HelloHTML**、表示するユーザーがクリックして、`HelloHTML`メッセージ ボックスです。  
  
 今すぐビルドすることができ、[変更 DHTML コントロールをテスト](../atl/testing-the-modified-atl-dhtml-control.md)です。  
  
## <a name="see-also"></a>関連項目  
 [DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)

