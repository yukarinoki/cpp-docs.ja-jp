---
title: ATL シンプル オブジェクトの追加
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.adding.atl
helpviewer_keywords:
- ATL projects, adding objects
- objects [ATL]
- ATL, simple objects
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
ms.openlocfilehash: 85c19c483ff27bd34431ec163e3baadac1855236
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499347"
---
# <a name="adding-an-atl-simple-object"></a>ATL シンプル オブジェクトの追加

ATL (Active Template Library) オブジェクトをプロジェクトに追加するには、atl アプリケーションとして、または ATL サポートを含む MFC アプリケーションとしてプロジェクトが作成されている必要があります。 Atl [プロジェクトウィザード](../../atl/reference/atl-project-wizard.md) を使用して atl アプリケーションを作成するか、mfc アプリケーション [に atl オブジェクトを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) して、mfc アプリケーションの atl サポートを実装することができます。

新しい ATL オブジェクトを最初に作成するときに COM インターフェイスを定義することも、**クラスビュー**のショートカットメニューから [[インターフェイスの実装](../../ide/implementing-an-interface-visual-cpp.md#implement-interface-wizard)] コマンドを使用して後で追加することもできます。

## <a name="to-add-an-atl-simple-object-to-your-atl-com-project"></a>Atl COM プロジェクトに ATL simple オブジェクトを追加するには

1. **ソリューションエクスプローラー**または[クラスビュー](/visualstudio/ide/viewing-the-structure-of-code)で、ATL simple オブジェクトを追加するプロジェクトの名前を右クリックします。

1. ショートカットメニューの [ **追加**] をクリックし、[ **クラスの追加**] をクリックします。

1. [ [クラスの追加](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) ] ダイアログボックスの [ **テンプレート** ] ペインで、[ **atl simple object**] をクリックし、[ **開く** ] をクリックして [atl シンプルオブジェクトウィザード](../../atl/reference/atl-simple-object-wizard.md)を表示します。

1. **ATL シンプルオブジェクト**ウィザードの [[オプション](../../atl/reference/options-atl-simple-object-wizard.md)] ページで、プロジェクトの追加オプションを設定します。

1. [ **完了** ] をクリックして、プロジェクトにオブジェクトを追加します。

## <a name="see-also"></a>関連項目

[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL プロジェクトでの新しいインターフェイスの追加](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[オブジェクトへの接続ポイントの追加](../../atl/adding-connection-points-to-an-object.md)<br/>
[メソッドの追加](../../ide/adding-a-method-visual-cpp.md)<br/>
[MFC クラス](../../mfc/reference/adding-an-mfc-class.md)<br/>
[一般 C++ クラスの追加](../../ide/adding-a-generic-cpp-class.md)
