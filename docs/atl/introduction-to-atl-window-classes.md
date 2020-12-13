---
description: '詳細情報: ATL ウィンドウクラスの概要'
title: ATL ウィンドウクラスの概要
ms.date: 11/04/2016
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
ms.openlocfilehash: 54a9d9764450025e51f9fac368a3434ca786fe09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152725"
---
# <a name="introduction-to-atl-window-classes"></a>ATL ウィンドウクラスの概要

次の ATL クラスは、ウィンドウを実装および操作するように設計されています。

- [CWindow](../atl/reference/cwindow-class.md) を使用すると、ウィンドウハンドルをオブジェクトにアタッチでき `CWindow` ます。 次 `CWindow` に、メソッドを呼び出してウィンドウを操作します。

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) を使用すると、新しいウィンドウを実装し、メッセージマップを使用してメッセージを処理できます。 新しい Windows クラスに基づいてウィンドウを作成したり、既存のクラスをスーパークラスにしたり、既存のウィンドウをサブクラス化したりすることができます。

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) を使用すると、モーダルまたはモードレスのダイアログボックスを実装し、メッセージマップを使用してメッセージを処理できます。

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) は、メッセージマップが別のクラスに含まれているウィンドウを実装する、事前に構築されたクラスです。 を使用する `CContainedWindowT` と、メッセージ処理を1つのクラスで集中管理できます。

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) を使用すると、ActiveX コントロールをホストするダイアログボックス (モーダルまたはモードレス) を実装できます。

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) を使用すると、基本的な機能を備えたモーダルダイアログボックスを実装できます。

- [CAxWindow](../atl/reference/caxwindow-class.md) を使用すると、ActiveX コントロールをホストするウィンドウを実装できます。

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) を使用すると、ライセンスされた ActiveX コントロールをホストするウィンドウを実装できます。

ATL には、特定のウィンドウクラスに加えて、ATL ウィンドウオブジェクトの実装を容易にするように設計されたいくつかのクラスが用意されています。 制限事項は次のとおりです。

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) は、新しいウィンドウクラスの情報を管理します。

- [CWinTraits](../atl/reference/cwintraits-class.md) と [CWINTRAITSOR](../atl/reference/cwintraitsor-class.md) は、ATL ウィンドウオブジェクトの特徴を標準化するための簡単な方法を提供します。

## <a name="see-also"></a>関連項目

[ウィンドウクラス](../atl/atl-window-classes.md)
