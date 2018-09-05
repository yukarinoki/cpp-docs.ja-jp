---
title: ATL ウィンドウ クラスの概要 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbd433eb024e7715c065a005ce06d38a086a5072
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765494"
---
# <a name="introduction-to-atl-window-classes"></a>ATL ウィンドウ クラスの概要

実装し、ウィンドウの操作は、次の ATL クラスは設計されています。

- [CWindow](../atl/reference/cwindow-class.md)にウィンドウ ハンドルをアタッチすることができます、`CWindow`オブジェクト。 呼び出して`CWindow`ウィンドウを操作するメソッド。

- [CWindowImpl](../atl/reference/cwindowimpl-class.md)新しいウィンドウを実装し、メッセージ マップでのメッセージを処理することができます。 作成ウィンドウでは、既存のウィンドウを新しい Windows クラス、スーパークラス既存のクラスまたはサブクラスに基づいています。

- [CDialogImpl](../atl/reference/cdialogimpl-class.md)モーダルまたは、メッセージ マップでのモードレス ダイアログ ボックスとプロセスのメッセージを実装することができます。

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)は別のクラスのメッセージ マップが含まれているウィンドウを実装する事前構築済みクラスです。 使用して`CContainedWindowT`1 つのクラスでのメッセージ処理を一元化することができます。

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) ActiveX コントロールをホストする ダイアログ ボックス (モーダルまたはモードレス) を実装することができます。

- [CSimpleDialog](../atl/reference/csimpledialog-class.md)基本的な機能を持つモーダル ダイアログ ボックスを実装することができます。

- [CAxWindow](../atl/reference/caxwindow-class.md) ActiveX コントロールをホストするウィンドウを実装することができます。

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md)ライセンスされた ActiveX コントロールをホストするウィンドウを実装することができます。

だけでなく、特定のウィンドウ クラスは、ATL は、ATL ウィンドウ オブジェクトの実装を容易に設計されています。 いくつかのクラスを提供します。 それらは次のとおりです。

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md)新しいウィンドウ クラスの情報を管理します。

- [CWinTraits](../atl/reference/cwintraits-class.md)と[CWinTraitsOR](../atl/reference/cwintraitsor-class.md) ATL ウィンドウ オブジェクトの特性を標準化する単純なメソッドを提供します。

## <a name="see-also"></a>関連項目

[ウィンドウ クラス](../atl/atl-window-classes.md)

