---
title: ActiveX コントロールからのクラスの追加 (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f9e7d8ea0e3b21b06d73e187a4f45c53cd896cf
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250485"
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>ActiveX コントロールからのクラスの追加 (Visual C++)

このウィザードを使用すると、使用可能な ActiveX コントロールのインターフェイスからの MFC クラスを作成できます。 MFC クラスは、[MFC アプリケーション](../mfc/reference/creating-an-mfc-application.md)、[MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md)、または [MFC ActiveX コントロール](../mfc/reference/creating-an-mfc-activex-control.md)に追加できます。

> [!WARNING]
> Visual Studio 2017 バージョン 15.9 では、このコード ウィザードは非推奨になっており、Visual Studio の今後のバージョンで削除されます。 このウィザードはほとんど使用されません。 このウィザードを削除しても、ATL と MFC の一般的なサポートには影響ありません。 この非推奨に関するご意見を共有したい場合は、[こちらのアンケート](https://www.surveymonkey.com/r/QDWKKCN)にお答えください。 お客様のご意見は私どもにとって重要です。

> [!NOTE]
>  ActiveX コントロールからクラスを追加するのに、Automation を有効にして MFC プロジェクトを作成する必要はありません。

ActiveX コントロールは、コンポーネント オブジェクト モデル (COM: Component Object Model) に基づく再利用可能なソフトウェア コンポーネントです。多岐にわたる OLE の機能をサポートしており、さまざまなソフトウェアの要件に合わせてカスタマイズできます。 ActiveX コントロールは、通常の ActiveX コントロール コンテナー内と、インターネット上の WWW (World Wide Web) ページの両方で使用できるように設計されています。

### <a name="to-add-an-mfc-class-from-an-activex-control"></a>ActiveX コントロールから MFC クラスを追加するには

1. **ソリューション エクスプローラー**または[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)のいずれかで、ActiveX コントロール クラスを追加するプロジェクト名を右クリックします。

1. ショートカット メニューの **[追加]**、**[クラスの追加]** を順にクリックします。

1. [[クラスの追加]](../ide/add-class-dialog-box.md) ダイアログ ボックスの [テンプレート] ウィンドウで、**[ActiveX コントロールの MFC クラス]**、**[開く]** を順にクリックして、[ActiveX コントロール クラス追加ウィザード](../ide/add-class-from-activex-control-wizard.md)を表示します。

ウィザードでは、ActiveX コントロールに 1 つ以上インターフェイスを追加できます。 同様に、ウィザードの 1 回のセッションで、複数の ActiveX コントロールからクラスを作成できます。

クラスは、システムに登録されている ActiveX コントロールから登録することも、最初にシステムに登録せずに、タイプ ライブラリ ファイル (.tlb、.olb、.dll、.ocx、または .exe) にある ActiveX コントロールから追加することもできます。 ActiveX の登録の詳細については、「[OLE コントロールの登録](../mfc/reference/registering-ole-controls.md)」を参照してください。

ウィザードでは、選択した ActiveX コントロールから追加した各インターフェイスに対して、[CWnd](../mfc/reference/cwnd-class.md) または [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) から派生した MFC クラスが作成されます。

## <a name="see-also"></a>参照

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br>
[COM と ATL の概要](../atl/introduction-to-com-and-atl.md)