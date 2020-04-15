---
title: MFC COM
ms.date: 09/12/2018
f1_keywords:
- MFC COM (MFC)
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
ms.openlocfilehash: 514251475050e728be1959417ead1dbdf96e4800
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358199"
---
# <a name="mfc-com"></a>MFC COM

MFC のサブセットは COM をサポートするように設計されていますが、アクティブ テンプレート ライブラリ (ATL) のほとんどは COM プログラミング用に設計されています。 このトピックでは、MFC の COM のサポートについて説明します。

ActiveX コントロール、Active ドキュメント コンテインメント、OLE などアクティブなテクノロジは、コンポーネント オブジェクト モデル (COM) を使用して、ソフトウェア コンポーネントがネットワーク環境で相互に対話できるようにします。 アクティブなテクノロジを使用して、デスクトップまたはインターネット上で実行されるアプリケーションを作成できます。 詳細については、「 [COM の概要](../atl/introduction-to-com.md)」または「[コンポーネント オブジェクト モデル](/windows/win32/com/the-component-object-model)」を参照してください。

アクティブなテクノロジには、次のようなクライアント テクノロジとサーバー テクノロジの両方が含まれます。

- ActiveX コントロールは、Web サイトなどのコンテナで使用できる対話型オブジェクトです。 ActiveX コントロールの詳細については、以下を参照してください。

  - [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

  - [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)

  - [概要: インターネット](../mfc/mfc-internet-programming-basics.md)

  - [インターネットで使用する既存の ActiveX コントロールをアップグレードする](../mfc/upgrading-an-existing-activex-control.md)

  - [ActiveX コントロールのデバッグ](/visualstudio/debugger/how-to-debug-an-activex-control)

- アクティブ スクリプトは、ブラウザまたはサーバーから 1 つ以上の ActiveX コントロールの統合動作を制御します。 アクティブ スクリプトの詳細については、「[インターネット上のアクティブ なテクノロジ](../mfc/active-technology-on-the-internet.md)」を参照してください。

- [オートメーション](../mfc/automation.md)(以前は OLE オートメーション) を使用すると、あるアプリケーションが別のアプリケーションに実装されているオブジェクトを操作したり、オブジェクトを "公開" して操作できるようにします。

   自動化オブジェクトは、ローカルまたはリモート (ネットワーク経由でアクセス可能な別のマシン上) である可能性があります。 OLE オブジェクトと COM オブジェクトは、どちらもオートメーションを利用できます。

- このセクションでは、MFC を使用して COM コンポーネントを記述する方法についても[説明します。](../mfc/connection-points.md)

現在の OLE と呼ばれるもの、および現在アクティブ なテクノロジと呼ばれているものについては[、OLE](../mfc/ole-in-mfc.md)に関するトピックを参照してください。

## <a name="in-this-section"></a>このセクションの内容

[Active ドキュメント コンテインメント](../mfc/active-document-containment.md)

[オートメーション](../mfc/automation.md)

[接続ポイント](../mfc/connection-points.md)

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)
