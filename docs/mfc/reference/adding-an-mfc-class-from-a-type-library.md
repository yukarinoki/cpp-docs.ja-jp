---
title: タイプ ライブラリからの MFC クラスの追加
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: 45bad00155cc1587980e6f3b25843a7a22e7e754
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503036"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>タイプ ライブラリからの MFC クラスの追加

このウィザードを使用して、使用可能なタイプライブラリのインターフェイスから MFC クラスを作成します。 MFC クラスは、[MFC アプリケーション](../../mfc/reference/creating-an-mfc-application.md)、[MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)、または [MFC ActiveX コントロール](../../mfc/reference/creating-an-mfc-activex-control.md)に追加できます。

> [!NOTE]
> タイプライブラリからクラスを追加するためのオートメーションが有効になっている MFC プロジェクトを作成する必要はありません。

タイプライブラリには、コンポーネントによって公開されるインターフェイスのバイナリ記述が含まれており、そのパラメーターと戻り値の型と共にメソッドが定義されています。 タイプライブラリは、Typelib からクラスを追加ウィザードの [ **使用できるタイプライブラリ** ] の一覧に表示されるように登録されている必要があります。

### <a name="to-add-an-mfc-class-from-a-type-library"></a>タイプライブラリから MFC クラスを追加するには

1. **ソリューションエクスプローラー**または[クラスビュー](/visualstudio/ide/viewing-the-structure-of-code)で、クラスを追加するプロジェクトの名前を右クリックします。

1. ショートカットメニューの [ **追加**] をクリックし、[ **クラスの追加**] をクリックします。

1. [ [クラスの追加](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) ] ダイアログボックスの [テンプレート] ペインで、[ **Typelib からの MFC クラス**] をクリックし、[ **開く** ] をクリックして、 [typelib からクラスを追加ウィザード](../../mfc/reference/add-class-from-typelib-wizard.md)を表示します。

ウィザードでは、タイプライブラリに複数のクラスを追加できます。 同様に、1つのウィザードセッションで複数のタイプライブラリのクラスを追加することもできます。

ウィザードでは、選択したタイプライブラリから追加するインターフェイスごとに、 [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)から派生した MFC クラスが作成されます。 `COleDispatchDriver` OLE オートメーションのクライアント側を実装します。

## <a name="see-also"></a>関連項目

[オートメーションクライアント](../../mfc/automation-clients.md)<br/>
[オートメーションクライアント: タイプライブラリの使用](../../mfc/automation-clients-using-type-libraries.md)
