---
title: DHTML から C++ コードを呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9e369396c68a041dc5fe027802859c6071e50e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355462"
---
# <a name="calling-c-code-from-dhtml"></a>DHTML から C++ コードを呼び出す
DHTML コントロールは、テスト コンテナーまたは Internet Explorer などのコンテナーでホストすることができます。 参照してください[プロパティのテストおよびテスト コンテナーでイベント](../mfc/testing-properties-and-events-with-test-container.md)テスト コンテナーにアクセスする方法についてはします。  
  
 コントロールをホストしているコンテナーは、通常の制御のインターフェイスを使用して、コントロールと通信します。 DHTML では、C++ コードと、HTML リソースと通信するには、"UI"で終わるディスパッチ インターフェイスを使用します。 [ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)、これらの各インターフェイスによって呼び出されるメソッドの追加を練習することができます。  
  
 DHTML から C++ コードの呼び出しの例を参照する[DHTML コントロールを作成](../atl/creating-an-atl-dhtml-control.md)ATL コントロール ウィザードを使用して、HTML ファイルおよびヘッダー ファイルでコードを調べます。  
  
## <a name="declaring-webbrowser-methods-in-the-header-file"></a>ヘッダー ファイル内の WebBrowser メソッドを宣言します。  
 DHTML UI から C++ メソッドを呼び出すには、コントロールの UI インターフェイスにメソッドを追加する必要があります。 たとえば、ATL コントロール ウィザードによって作成されたヘッダー ファイルには、C++ メソッドが含まれます。 `OnClick`、ウィザードで生成されたコントロールの UI インターフェイスのメンバーであります。  
  
 調べる`OnClick`コントロールの .h ファイルには。  
  
 [!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]  
  
 最初のパラメーターでは、 `pdispBody`、本体オブジェクトのディスパッチ インターフェイスへのポインターです。 2 番目のパラメーターでは、`varColor`コントロールに適用する色を指定します。  
  
## <a name="calling-c-code-in-the-html-file"></a>HTML ファイルでの C++ コードを呼び出す  
 ヘッダー ファイル内の WebBrowser メソッドが宣言されると、HTML ファイルからのメソッドを呼び出すことができます。 ATL コントロール ウィザードは、次の 3 つのディスパッチ メソッドを挿入します。 HTML ファイルで予告: 次の 3 つ`OnClick`コントロールの背景色を変更するメッセージをディスパッチするメソッド。  
  
 HTML ファイル内のメソッドのいずれかを調べます。  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 ウィンドウの外部メソッドの上の HTML コードで`OnClick`ボタンのタグの一部として呼び出されます。 メソッドには 2 つのパラメーター:`theBody`を参照する HTML ドキュメントの本文と`"red"`ボタンがクリックされたときに、コントロールの背景色が赤に変更されることを示します。 `Red`ボタンのラベルは、次のタグ。  
  
 参照してください[ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)詳細については、独自のメソッドを提供します。 参照してください[DHTML コントロール プロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)HTML ファイルの詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)

