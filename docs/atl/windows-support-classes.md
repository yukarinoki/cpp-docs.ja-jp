---
description: 詳細については、「Windows サポートクラス」を参照してください。
title: Windows サポートクラス (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
ms.openlocfilehash: c88a6ef878a428581ca090e78b2fac3b5e02131d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138062"
---
# <a name="windows-support-classes"></a>Windows サポートクラス

次のクラスは、windows のサポートを提供します。

- [_U_MENUorID](../atl/reference/u-menuorid-class.md) およびのラッパーを提供 `CreateWindow` `CreateWindowEx` します。

- [CWindow](../atl/reference/cwindow-class.md) ウィンドウを操作するためのメソッドを格納します。 `CWindow` は、`CWindowImpl`、`CDialogImpl`、および `CContainedWindow` の基本クラスです。

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) 新しいウィンドウクラスに基づいてウィンドウを実装します。 では、ウィンドウをサブクラス化またはスーパークラス化することもできます。

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) ダイアログボックスを実装します。

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX コントロールをホストするダイアログボックス (モーダルまたはモードレス) を実装します。

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) 基本的な機能を備えたダイアログボックス (モーダルまたはモードレス) を実装します。

- [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX コントロールをホストするウィンドウを操作します。

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) ActiveX コントロールをホストし、ライセンスされた ActiveX コントロールのホストをサポートするウィンドウを操作するためのメソッドを提供します。

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) 別のオブジェクト内に含まれるウィンドウを実装します。

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 新しいウィンドウクラスの情報を管理します。

- [CDynamicChain](../atl/reference/cdynamicchain-class.md) では、メッセージマップの動的チェーンがサポートされています。

- [CMessageMap](../atl/reference/cmessagemap-class.md) オブジェクトが他のオブジェクトにメッセージマップを公開できるようにします。

- [CWinTraits](../atl/reference/cwintraits-class.md) ATL ウィンドウオブジェクトの特徴を標準化するための簡単な方法を提供します。

- [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) ウィンドウの作成に使用されるウィンドウスタイルおよび拡張スタイルの既定値を提供します。 これらの値は、論理 OR 演算子を使用して、ウィンドウの作成時に指定される値に追加されます。

## <a name="related-articles"></a>関連記事

[ATL ウィンドウクラス](../atl/atl-window-classes.md)

[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)<br/>
[メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)<br/>
[ウィンドウクラスマクロ](../atl/reference/window-class-macros.md)
