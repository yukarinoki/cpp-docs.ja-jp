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
ms.openlocfilehash: da194510938e3fe02eba5993182e811fdf2e1b7c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618011"
---
# <a name="mfc-com"></a>MFC COM

MFC のサブセットは COM をサポートするように設計されていますが、ほとんどの Active Template Library (ATL) は COM プログラミング向けに設計されています。 このセクションのトピックでは、MFC における COM のサポートについて説明します。

ActiveX コントロール、Active document コンテインメント、OLE などのアクティブなテクノロジでは、コンポーネントオブジェクトモデル (COM) を使用して、ソフトウェアコンポーネントが、作成された言語に関係なく、ネットワーク環境内で相互に通信できるようにします。 アクティブなテクノロジを使用して、デスクトップまたはインターネット上で実行されるアプリケーションを作成できます。 詳細については、「 [COM の概要](../atl/introduction-to-com.md)」または「[コンポーネントオブジェクトモデル](/windows/win32/com/the-component-object-model)」を参照してください。

アクティブなテクノロジには、クライアントとサーバーの両方のテクノロジが含まれます。次に例を示します。

- ActiveX コントロールは、Web サイトなどのコンテナーで使用できる対話型のオブジェクトです。 ActiveX コントロールの詳細については、以下を参照してください。

  - [MFC ActiveX コントロール](mfc-activex-controls.md)

  - [インターネット上の ActiveX コントロール](activex-controls-on-the-internet.md)

  - [概要: インターネット](mfc-internet-programming-basics.md)

  - [インターネットで使用する既存の ActiveX コントロールをアップグレードする](upgrading-an-existing-activex-control.md)

  - [ActiveX コントロールのデバッグ](/visualstudio/debugger/how-to-debug-an-activex-control)

- アクティブスクリプティングは、ブラウザーまたはサーバーからの1つ以上の ActiveX コントロールの統合動作を制御します。 アクティブスクリプティングの詳細については、「[インターネット上のアクティブなテクノロジ](active-technology-on-the-internet.md)」を参照してください。

- [オートメーション](automation.md)(以前の OLE オートメーション) を使用すると、あるアプリケーションで別のアプリケーションに実装されているオブジェクトを操作したり、オブジェクトを "公開" して操作できるようにしたりすることができます。

   自動オブジェクトは、ローカルまたはリモート (ネットワーク経由でアクセス可能な別のコンピューター上) である場合があります。 OLE オブジェクトと COM オブジェクトは、どちらもオートメーションを利用できます。

- このセクションでは、たとえば、[接続ポイント](connection-points.md)で MFC を使用して COM コンポーネントを記述する方法についても説明します。

まだ OLE と呼ばれているものについては、 [「ole」](ole-in-mfc.md)を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[Active ドキュメント コンテインメント](active-document-containment.md)

[Automation](automation.md)

[接続ポイント](connection-points.md)

[MFC ActiveX コントロール](mfc-activex-controls.md)

## <a name="see-also"></a>関連項目

[概念](mfc-concepts.md)
