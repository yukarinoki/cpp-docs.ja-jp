---
description: 詳細については、「MFC ActiveX コントロールウィザード」を参照してください。
title: MFC ActiveX コントロール ウィザード
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.mfc.ctl.overview
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
ms.openlocfilehash: f313f2a218c06a20eddbfff33e936109e4be2cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219266"
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX コントロール ウィザード

ActiveX コントロールは、特定の種類の [オートメーションサーバー](../../mfc/automation-servers.md)です。再利用可能なコンポーネントです。 ActiveX コントロールをホストするアプリケーションは、そのコントロールの [オートメーションクライアント](../../mfc/automation-clients.md) です。 このような再利用可能なコンポーネントを作成することが目的である場合は、このウィザードを使用してコントロールを作成します。 詳細については、「 [MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md) 」を参照してください。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](../activex-controls.md)」を参照してください。

または、 [Mfc アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)を使用して、オートメーションサーバー mfc アプリケーションを作成することもできます。

このウィザードで作成された ActiveX コントロールは、ユーザーインターフェイスを持つことができます。または、非表示にすることもできます。 このオプションは、ウィザードの [ [コントロールの設定](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) ] ページで指定できます。 Timer コントロールは、非表示にする ActiveX コントロールの一例です。

ActiveX コントロールは、複雑なユーザーインターフェイスを持つことができます。 一部のコントロールは、カプセル化されたフォームのようなものもあります。多くのフィールドを含む1つのコントロール (それぞれが Windows コントロール) です。 たとえば、MFC ActiveX コントロールとして実装されている自動パーツオブジェクトは、ユーザーが部品番号、パーツ名、およびその他の情報の読み取りと編集を行うことができる、フォームに似たユーザーインターフェイスを提供する場合があります。 詳細については、「 [MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md) 」を参照してください。

ActiveX オブジェクトのコンテナーを作成する必要がある場合は、「 [Activex コントロールコンテナーを作成](../../mfc/reference/creating-an-mfc-activex-control-container.md)する」を参照してください。

MFC スタータープログラムには、C++ ソース (.cpp) ファイル、リソース (.rc) ファイル、およびプロジェクト (.vcxproj) ファイルが含まれています。 これらのスターターファイルで生成されるコードは、MFC に基づいています。

次のサンプルリストは、ActiveX コントロールのタスクと拡張機能の種類を示しています。

- [ActiveX コントロールの最適化](../../mfc/mfc-activex-controls-optimization.md)

- [ActiveX コントロールへのストックイベントの追加](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [カスタムイベントの追加](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [ストックメソッドの追加](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [カスタムメソッドの追加](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [ストックプロパティの追加](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [カスタムプロパティの追加](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [ActiveX コントロールコンテナーでの ActiveX コントロールのプログラミング](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>概要

このウィザードページでは、作成する MFC ActiveX コントロールプロジェクトの現在のアプリケーション設定について説明します。 既定では、このウィザードでは、次のようなウィザード プロジェクトが作成されます。

- 既定のプロジェクトでは、実行時のライセンスまたはヘルプファイルが生成されません。 これらの既定の設定は、[ [アプリケーションの設定](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) ] ページで変更できます。 [ **概要** ] ページには、ActiveX コントロールウィザードのこのページで行った選択のみが反映されます。

- プロジェクトには、プロジェクトの名前に基づいて、コントロールクラスとプロパティページクラスが含まれています。 プロジェクト名とファイル名は、[ [コントロール名](../../mfc/reference/control-names-mfc-activex-control-wizard.md) ] ページで編集できます。

- コントロールは、既存の Windows コントロールはありません。コントロールが表示されたときにアクティブになり、ユーザーインターフェイスを持ち、[ **バージョン情報** ] ダイアログボックスを含みます。 これらの既定の設定は、[ [コントロールの設定](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) ] ページで変更できます。

## <a name="see-also"></a>関連項目

[Visual Studio プロジェクト - C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual Studio の C++ プロジェクトの種類](../../build/reference/visual-cpp-project-types.md)<br/>
[概念](../../atl/active-template-library-atl-concepts.md)
