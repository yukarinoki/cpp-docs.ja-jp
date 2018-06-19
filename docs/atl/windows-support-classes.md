---
title: Windows のサポート クラス (ATL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.windows
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2095e5141dfdd320bae0e7aa69ffd4b3c9fe9a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362083"
---
# <a name="windows-support-classes"></a>Windows のサポート クラス
次のクラスは、windows をサポートを提供します。  
  
-   [_U_MENUorID](../atl/reference/u-menuorid-class.md)用のラッパーを提供**CreateWindow**と**について**です。  
  
-   [CWindow](../atl/reference/cwindow-class.md)ウィンドウを操作するためのメソッドが含まれています。 `CWindow` は、`CWindowImpl`、`CDialogImpl`、および `CContainedWindow` の基本クラスです。  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md)新しいウィンドウ クラスに基づくウィンドウを実装します。 こともできますサブクラスまたはスーパークラス ウィンドウです。  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md)  ダイアログ ボックスを実装します。  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX コントロールをホストするダイアログ ボックス (モーダルまたはモードレス) を実装します。  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md)基本的な機能を持つ ダイアログ ボックス (モーダルまたはモードレス) を実装します。  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX コントロールをホストするウィンドウを操作します。  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) ActiveX コントロールをホストし、ライセンスされた ActiveX コントロールをホストするためのサポートがウィンドウを操作するためのメソッドを提供します。  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)別のオブジェクト内に含まれるウィンドウを実装します。  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md)新しいウィンドウ クラスの情報を管理します。  
  
-   [CDynamicChain](../atl/reference/cdynamicchain-class.md)メッセージ マップの動的な組み合わせをサポートしています。  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md)にそのメッセージを公開するオブジェクトが他のオブジェクトに対応付けが可能になります。  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) ATL ウィンドウ オブジェクトの特徴を標準化する単純なメソッドを提供します。  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md)ウィンドウ スタイルとウィンドウを作成するために使用する拡張スタイルの既定値を提供します。 ウィンドウの作成時に提供される値に、論理 OR 演算子を使用してこれらの値が追加されます。  
  
## <a name="related-articles"></a>関連トピック  
 [ATL ウィンドウ クラス](../atl/atl-window-classes.md)  
  
 [ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../atl/atl-class-overview.md)   
 [メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)   
 [Windows クラスに関するマクロ](../atl/reference/window-class-macros.md)

