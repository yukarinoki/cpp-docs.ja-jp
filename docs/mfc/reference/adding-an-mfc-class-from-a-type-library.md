---
title: タイプ ライブラリからの MFC クラスの追加
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: bf9c763a215a4880d5b0ad206f6a347341fea9eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371722"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>タイプ ライブラリからの MFC クラスの追加

このウィザードを使用して、使用可能なタイプ ライブラリのインターフェイスから MFC クラスを作成します。 MFC クラスは、[MFC アプリケーション](../../mfc/reference/creating-an-mfc-application.md)、[MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)、または [MFC ActiveX コントロール](../../mfc/reference/creating-an-mfc-activex-control.md)に追加できます。

> [!NOTE]
> タイプ ライブラリからクラスを追加するために、オートメーションを有効にした状態で MFC プロジェクトを作成する必要はありません。

タイプ ライブラリには、コンポーネントによって公開されるインターフェイスのバイナリ記述が含まれ、メソッドとそのパラメーターおよび戻り値の型が定義されます。 タイプ ライブラリが Typelib からクラスを追加ウィザードの **[使用可能なタイプ ライブラリ**] リストに表示されるようにするには、そのタイプ ライブラリを登録する必要があります。 詳細については、MSDN ライブラリの「内部分散 COM: タイプ ライブラリと言語の統合」を参照してください。

### <a name="to-add-an-mfc-class-from-a-type-library"></a>タイプ ライブラリから MFC クラスを追加するには

1. ソリューション**エクスプローラー**または[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)のいずれかで、クラスを追加するプロジェクトの名前を右クリックします。

1. ショートカット メニューの [**追加**] をクリックし、[**クラスの追加**] をクリックします。

1. [[クラスの追加](../../ide/add-class-dialog-box.md)] ダイアログ ボックスの [テンプレート] ペインで **、[Typelib から MFC クラス**] をクリックし、[**開く**] をクリックして[Typelib ウィザードからクラスを追加](../../mfc/reference/add-class-from-typelib-wizard.md)します。

ウィザードでは、タイプ ライブラリに複数のクラスを追加できます。 同様に、1 つのウィザード セッションで複数のタイプ ライブラリからクラスを追加できます。

ウィザードは、選択したタイプ ライブラリから追加するインターフェイスごとに[、COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)から派生した MFC クラスを作成します。 `COleDispatchDriver`は、OLE オートメーションのクライアント側を実装します。

## <a name="see-also"></a>関連項目

[オートメーション クライアント](../../mfc/automation-clients.md)<br/>
[オートメーション クライアント : タイプ ライブラリの使用](../../mfc/automation-clients-using-type-libraries.md)
